# Client Rates Filtering - Product Requirements Document

**Document Owner:** [Your Name] | **Last Updated:** 2026-03-11 | **Status:** Draft

*Example PRD generated with `/pm:prd-scaffold`*

---

## 1. Executive Summary

Today, clients using Digital Client Rate Sheets (DCRS) need to scroll through hundreds of rate sheet entries to find relevant rates for their shipments. When clients have 50+ origin/destination pairs across multiple tradelanes, this manual scanning process takes 5-10 minutes per quote and leads to clients using outdated rates or missing better options.

In Q2 2026, we will launch Client Rates Filtering, allowing clients to quickly filter their rate sheets by origin, destination, tradelane, and service level. This will reduce rate discovery time from 5-10 minutes to under 30 seconds, improving quote conversion and reducing client frustration.

We will limit the initial launch to basic filtering on the Rates landing page. Advanced features like saved filter presets, multi-select combinations, and filter-based notifications will be deferred to Phase 2 based on user feedback and usage data.

---

## 2. Success Metrics

**How we'll know we succeeded:**

| Metric | Baseline | Target | Measurement Method |
|--------|----------|--------|-------------------|
| Average time to find rate | 5-10 minutes | < 30 seconds | Mixpanel: time between Rates page load and rate detail view |
| Filter usage rate | 0% (doesn't exist) | 70% of sessions | Mixpanel: % of Rates page sessions using filters |
| Quote creation from Rates | 45% | 65% | Conversion rate: Rates page view → Quote created |
| Client satisfaction (NPS) | TBD | +10 points | Post-quote NPS survey |

**Metric Categories:**
- **Launch Metrics:** Feature deployed to 100% clients with Rates, zero errors
- **Adoption Metrics:** 70% of users with 20+ rates use filters within first week
- **Business Impact:** 20% increase in instant book conversion, 15% reduction in AE quote requests
- **User Satisfaction:** Positive feedback in user interviews, <5 support tickets/week

*Note: Use `/pm:success-metrics` for deeper metrics exploration and baseline establishment.*

---

## 3. Definitions

**Key terms used in this document:**

| Term | Definition |
|------|------------|
| **Rates** | Negotiated or saved pricing agreements between client and Flexport for freight services |
| **Rate Sheet** | Collection of rates for a specific client, typically organized by origin-destination pairs |
| **Tradelane** | High-level geographic route category (e.g., Asia-North America, Europe-Asia) |
| **Service Level** | Speed/reliability tier for freight service (e.g., Standard, Express, Flexible) |
| **DCRS** | Digital Client Rate Sheets - Internal tool for AEs to manage client rates |

---

## 4. User Personas

| # | Persona | Description | Goals | Challenges |
|---|---------|-------------|-------|------------|
| 1 | Enterprise Client | Large shipper with 50+ negotiated lanes across multiple tradelanes | Quickly find the right rate for each shipment without contacting AE | Too many rates to scan manually, often uses wrong rate or outdated pricing |
| 2 | Operations Associate | Books shipments on behalf of clients using their negotiated rates | Find correct rate quickly to generate accurate quotes | Wastes time scrolling through irrelevant rates, sometimes misses better options |
| 3 | Account Executive | Manages client rate sheets and supports booking questions | Reduce inbound "which rate should I use?" questions from clients | Clients can't find rates themselves, leading to unnecessary AE involvement |

---

## 5. User Journey: Current vs. Future State

**Current State (Before):**
Client logs into Rates page, sees 150 rate sheet entries in one long list, manually scrolls through looking for Shanghai→Los Angeles rates, scans dates to find current validity, takes 5-10 minutes, sometimes gives up and calls AE.

**Future State (After):**
Client logs into Rates page, selects "China" origin filter and "US" destination filter, sees 12 relevant rates, selects Shanghai→Los Angeles specifically, finds current rate in 30 seconds, proceeds to instant book.

**Journey Comparison:**

| Step | Current State | Future State | Improvement |
|------|--------------|--------------|-------------|
| 1. Access Rates | Navigate to Rates page | Navigate to Rates page | (Same) |
| 2. Find relevant rates | Manually scroll through 150+ entries | Apply origin/destination filters | 5-10 min → 10 sec |
| 3. Identify right rate | Scan dates, compare service levels | View filtered 10-15 rates | Cognitive load reduced 90% |
| 4. Validate selection | Check with AE or hope it's correct | Confidence from targeted results | Eliminates verification step |
| 5. Book | Proceed to instant book or abandon | Proceed to instant book | 20% higher conversion |

---

## 6. Requirements

### Epic 1: Filter UI and Core Functionality
*Allow users to filter rates by key attributes on the Rates landing page*

| # | Requirement | User Story & Acceptance Criteria | Priority |
|---|-------------|----------------------------------|----------|
| 1.1 | Filter Panel Display | **User Story:**<br>As a client, I want to see available filters on the Rates page, so that I can quickly understand what filtering options exist.<br><br>**AC 1.1.1**<br>Given a client is on the Rates page<br>When the page loads<br>Then the user sees a filter panel on the left side with filter categories: Origin Country, Origin City/Port, Destination Country, Destination City/Port, Tradelane, Service Level<br><br>**AC 1.1.2**<br>Given the filter panel is displayed<br>When the user has not selected any filters<br>Then all filters show "All" as the default selection<br>And the full unfiltered list of rates is displayed | P0 |
| 1.2 | Origin Filters | **User Story:**<br>As a client, I want to filter rates by origin location, so that I can see only rates relevant to where my cargo is shipping from.<br><br>**AC 1.2.1**<br>Given a client clicks on the "Origin Country" filter<br>When the dropdown opens<br>Then the user sees a list of all countries that appear as origins in their rate sheets, sorted alphabetically<br><br>**AC 1.2.2**<br>Given a client selects "China" in Origin Country filter<br>When the selection is made<br>Then only rates with China as origin country are displayed<br>And the rate count updates to show "Showing X of Y rates"<br>And other filters update to show only relevant options (e.g., only Chinese cities in Origin City filter) | P0 |
| 1.3 | Destination Filters | **User Story:**<br>As a client, I want to filter rates by destination location, so that I can see only rates going to where I need to ship.<br><br>**AC 1.3.1**<br>Given a client clicks on the "Destination Country" filter<br>When the dropdown opens<br>Then the user sees a list of all countries that appear as destinations in their rate sheets, sorted alphabetically<br><br>**AC 1.3.2**<br>Given a client has selected Origin filters<br>When they open the Destination Country filter<br>Then only destination countries that have rates matching the origin filters are shown (dependent filtering) | P0 |
| 1.4 | Tradelane Filter | **User Story:**<br>As a client, I want to filter by tradelane, so that I can quickly narrow to a geographic region without specifying exact cities.<br><br>**AC 1.4.1**<br>Given a client clicks on "Tradelane" filter<br>When the dropdown opens<br>Then the user sees: Asia-North America, Asia-Europe, Europe-North America, Intra-Asia, (and any other tradelanes in their rate sheets)<br><br>**AC 1.4.2**<br>Given a client selects "Asia-North America" tradelane<br>When the filter is applied<br>Then only rates with origins in Asia and destinations in North America are displayed | P0 |
| 1.5 | Service Level Filter | **User Story:**<br>As a client, I want to filter by service level, so that I can find rates matching my speed/cost requirements.<br><br>**AC 1.5.1**<br>Given a client clicks on "Service Level" filter<br>When the dropdown opens<br>Then the user sees: Standard, Express, Flexible, (and any other service levels in their rates)<br><br>**AC 1.5.2**<br>Given a client selects "Express" service level<br>When the filter is applied<br>Then only rates with Express service level are displayed | P0 |
| 1.6 | Clear Filters | **User Story:**<br>As a client, I want to clear all filters at once, so that I can start over without manually removing each filter.<br><br>**AC 1.6.1**<br>Given a client has applied one or more filters<br>When the user clicks "Clear all filters" button<br>Then all filter selections reset to "All"<br>And the full unfiltered rate list is displayed<br><br>**AC 1.6.2**<br>Given no filters are applied<br>When the page is displayed<br>Then the "Clear all filters" button is disabled or hidden | P0 |
| 1.7 | Filter Result Count | **User Story:**<br>As a client, I want to see how many rates match my filters, so that I know if I need to broaden or narrow my search.<br><br>**AC 1.7.1**<br>Given a client applies any filter<br>When the filter is applied<br>Then the UI displays "Showing X of Y rates" above the rate list<br>And X = number of rates matching filters<br>And Y = total number of rates<br><br>**AC 1.7.2**<br>Given filters result in zero matches<br>When no rates match<br>Then the UI displays "No rates match your filters" with a prompt to adjust filters or clear all | P0 |

### Epic 2: Filter Persistence and Performance
*Ensure filters remain applied during session and perform well with large rate sheets*

| # | Requirement | User Story & Acceptance Criteria | Priority |
|---|-------------|----------------------------------|----------|
| 2.1 | Session Persistence | **User Story:**<br>As a client, I want my filter selections to persist when I navigate away and back to Rates, so that I don't have to re-apply them.<br><br>**AC 2.1.1**<br>Given a client has applied filters on the Rates page<br>When they navigate to a rate detail page and return to Rates<br>Then the previously applied filters are still active<br>And the filtered rate list is displayed<br><br>**AC 2.1.2**<br>Given a client has applied filters<br>When they log out and log back in<br>Then filters reset to default (all filters clear) - no persistence across sessions | P0 |
| 2.2 | Performance | **User Story:**<br>As a client with a large rate sheet, I want filtering to be instantaneous, so that my workflow isn't slowed down.<br><br>**AC 2.2.1**<br>Given a client has 500+ rates in their rate sheet<br>When they apply any filter<br>Then the filtered results appear in < 500ms<br><br>**AC 2.2.2**<br>Given a client applies multiple filters in sequence<br>When each filter is applied<br>Then the UI updates without page reload (client-side filtering) | P0 |

---

## 7. Out of Scope / Deferred (P1/P2)

**P1 - Important but not MVP:**
- Saved filter presets ("Save this filter combination as 'Asia Imports'")
- Multi-select within filters (select multiple origin countries at once)
- Free-text search within filter options
- Filter by container type (20ft, 40ft, etc.)
- Filter by validity date range (show only rates valid in next 30 days)
- Advanced filters: carrier, rate type (spot vs contract)

**P2 - Future Consideration:**
- Smart filter suggestions based on booking history
- Filter-based notifications ("Alert me when rates matching these filters update")
- Shared filter presets across team members
- Filter by allocation availability (for NAC rates)
- Export filtered rate list to CSV

---

## 8. Technical Considerations

**Dependencies:**
- Rates API must return all filterable attributes for each rate
- Frontend state management for filter selections
- Tradelane data model in backend (if not already available)

**Constraints:**
- Must work on mobile (filter panel collapses to modal on small screens)
- Filter options must load from actual rate data (no hardcoded lists)
- Must support 1000+ rate sheets without performance degradation

**Open Questions:**
- [ ] Should filters use AND logic (all filters must match) or OR logic (any filter matches)? **Decision: AND logic for MVP**
- [ ] How do we handle ports vs cities in location filters? **Decision: Show unified list with "City (Port)" format**
- [ ] Should dependent filtering be strict (hide unavailable options) or show disabled? **Decision: Hide unavailable for cleaner UX**

**Non-Functional Requirements:**
- Performance: Filtering completes in < 500ms for 1000 rates
- Accessibility: Keyboard navigation through all filters, screen reader compatible
- Analytics: Track which filters are used most, which combinations are common

---

## 9. Phasing

| Phase | Description | Target | Key Features |
|-------|-------------|--------|--------------|
| Phase 1 (MVP) | Basic filtering by location, tradelane, service level | Q2 2026 | Origin/Destination filters, Tradelane, Service Level, Clear All, Session persistence |
| Phase 2 (MLP) | Enhanced filtering with multi-select and saved presets | Q3 2026 | Multi-select filters, Saved filter presets, Free-text search, Container type filter |
| Phase 3 | Advanced features and intelligence | Q4 2026 | Smart suggestions, Filter-based notifications, Team shared presets |

---

## Appendix A: Visual Summary for Stakeholders

**1-Page Executive Overview**

### The Problem
Clients with 50+ rate sheet entries waste 5-10 minutes scrolling through irrelevant rates, leading to frustration, wrong rate selection, and abandoned instant bookings.

### The Solution
Add intuitive filtering by origin, destination, tradelane, and service level to the Rates page, reducing rate discovery from 5-10 minutes to under 30 seconds.

### Who It Helps
- **Enterprise Clients:** Find relevant rates instantly without AE support
- **Operations Associates:** Book faster with accurate rate selection
- **Account Executives:** Reduce inbound support questions by 30%

### Expected Impact
- Time to find rate: 5-10 min → 30 sec (90% reduction)
- Filter usage: 70% of Rates sessions
- Instant book conversion: 45% → 65%
- Support tickets: 25% reduction

### User Journey Visualization

```
CURRENT STATE:
Client → Rates page → Scroll 150 entries → Scan manually → Find rate (maybe) → Abandon or Call AE
         ⏱️ 10 sec    ⏱️ 5-10 min        🤯 Frustrating   ❌ 45% convert  ☎️ 30% call AE

FUTURE STATE:
Client → Rates page → Apply 2-3 filters → View 12 matches → Select rate → Instant book
         ⏱️ 10 sec    ⏱️ 10 sec           😊 Easy          ⏱️ 10 sec      ✅ 65% convert
```

### Timeline
- **Phase 1 (MVP):** Q2 2026 - Basic origin/destination/tradelane/service level filtering
- **Phase 2 (MLP):** Q3 2026 - Multi-select, saved presets, advanced filters
- **Phase 3:** Q4 2026 - Smart suggestions, notifications

---

*Generated with `/pm:prd-scaffold` - 2026-03-11*
*Next steps: Review with design team, validate with 3-5 enterprise clients, refine metrics with `/pm:success-metrics`*
