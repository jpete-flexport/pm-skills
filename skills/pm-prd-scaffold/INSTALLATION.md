# Installation Guide - PM PRD Scaffold Skill

Complete installation instructions for Flexport Product Managers.

---

## Prerequisites

### 1. Claude Code Installed

You need Claude Code CLI tool installed. To verify:

```bash
claude --version
```

If not installed, follow Flexport's Claude Code setup guide.

### 2. Skills Directory Exists

Check if your skills directory exists:

```bash
ls ~/.claude/skills
```

If it doesn't exist, create it:

```bash
mkdir -p ~/.claude/skills
```

---

## Installation Steps

### Option 1: From GitHub (Recommended)

Once this is added to Flexport's GitHub:

```bash
# Clone the repository
cd ~/Downloads
git clone [GITHUB_URL]/pm-skills

# Copy the skill
cp -r pm-skills/pm-prd-scaffold ~/.claude/skills/

# Verify
ls ~/.claude/skills/pm-prd-scaffold
```

### Option 2: From Shared Drive

If shared via Google Drive or internal file share:

```bash
# Download and extract the zip file
cd ~/Downloads
unzip pm-prd-scaffold.zip

# Copy to skills directory
cp -r pm-prd-scaffold ~/.claude/skills/

# Verify
ls ~/.claude/skills/pm-prd-scaffold
```

### Option 3: Manual Setup

If you received individual files:

```bash
# Create skill directory
mkdir -p ~/.claude/skills/pm-prd-scaffold/resources

# Copy files
cp SKILL.md ~/.claude/skills/pm-prd-scaffold/
cp README.md ~/.claude/skills/pm-prd-scaffold/
cp resources/*.md ~/.claude/skills/pm-prd-scaffold/resources/

# Verify structure
ls -R ~/.claude/skills/pm-prd-scaffold
```

---

## Verification

### 1. Check File Structure

You should have:

```
~/.claude/skills/pm-prd-scaffold/
├── SKILL.md                    # Main skill logic (required)
├── README.md                   # Documentation
└── resources/
    ├── prd_patterns.md         # Writing patterns
    └── quick_reference.md      # Quick tips
```

Verify with:

```bash
tree ~/.claude/skills/pm-prd-scaffold
```

Or:

```bash
find ~/.claude/skills/pm-prd-scaffold -type f
```

### 2. Restart Claude Code

If Claude Code was already running:

```bash
# Exit current Claude Code session (Ctrl+D or 'exit')
# Then restart
claude
```

### 3. Test the Skill

In Claude Code, try:

```
/pm:prd-scaffold
```

You should see the skill start with:

```
Are you in Discovery mode (still gathering insights) or PRD mode (insights ready)?
```

If you see this, installation was successful! Type `stop` to exit.

---

## Troubleshooting

### Issue: Skill not found

**Symptom:** `/pm:prd-scaffold` returns "skill not found"

**Solutions:**

1. **Check file location:**
   ```bash
   ls ~/.claude/skills/pm-prd-scaffold/SKILL.md
   ```
   If file doesn't exist, reinstall.

2. **Check filename:**
   Must be `SKILL.md` (all caps), not `skill.md` or `Skill.md`

3. **Restart Claude Code:**
   Exit and restart for skills to be detected.

4. **Check permissions:**
   ```bash
   chmod -R 755 ~/.claude/skills/pm-prd-scaffold
   ```

### Issue: Skill starts but behaves incorrectly

**Symptom:** Skill invokes but doesn't follow expected flow

**Solutions:**

1. **Verify SKILL.md content:**
   ```bash
   head -20 ~/.claude/skills/pm-prd-scaffold/SKILL.md
   ```
   Should start with YAML frontmatter:
   ```yaml
   ---
   name: pm:prd-scaffold
   description: Generate structured PRD...
   version: 1.0.0
   ---
   ```

2. **Check for file corruption:**
   Re-copy the files from source.

3. **Review resource files:**
   ```bash
   ls ~/.claude/skills/pm-prd-scaffold/resources/
   ```
   Should contain `prd_patterns.md` and `quick_reference.md`

### Issue: Permission denied

**Symptom:** Cannot copy files to `~/.claude/skills`

**Solutions:**

1. **Check directory permissions:**
   ```bash
   ls -la ~/.claude/
   ```

2. **Create directory with correct permissions:**
   ```bash
   mkdir -p ~/.claude/skills
   chmod 755 ~/.claude/skills
   ```

3. **Use sudo if necessary (not recommended):**
   ```bash
   sudo cp -r pm-prd-scaffold ~/.claude/skills/
   sudo chown -R $USER ~/.claude/skills/pm-prd-scaffold
   ```

### Issue: Skill conflicts with existing skills

**Symptom:** Error about duplicate skill name

**Solution:**

This skill is uniquely named `pm:prd-scaffold` and should not conflict. If you have a naming conflict:

1. Check for other skills with similar names:
   ```bash
   ls ~/.claude/skills/
   ```

2. Rename this skill (not recommended):
   Edit `SKILL.md` and change the `name:` field

---

## Updating the Skill

### Update from GitHub

```bash
cd ~/Downloads/pm-skills
git pull origin main
cp -r pm-prd-scaffold ~/.claude/skills/
```

### Manual Update

Replace the files:

```bash
# Backup existing (optional)
cp -r ~/.claude/skills/pm-prd-scaffold ~/.claude/skills/pm-prd-scaffold.backup

# Copy new version
cp -r /path/to/new/pm-prd-scaffold ~/.claude/skills/

# Restart Claude Code
```

### Check Version

View the version in SKILL.md:

```bash
head -10 ~/.claude/skills/pm-prd-scaffold/SKILL.md
```

Look for:
```yaml
version: 1.0.0
```

---

## Uninstalling

To remove the skill:

```bash
rm -rf ~/.claude/skills/pm-prd-scaffold
```

Then restart Claude Code.

---

## Multiple Installations

### Personal vs Team Installations

You can have different versions:

**Personal customizations:**
```bash
~/.claude/skills/pm-prd-scaffold/
```

**Team shared version (via Git):**
```bash
~/flexport/pm-skills/pm-prd-scaffold/
# Create symlink
ln -s ~/flexport/pm-skills/pm-prd-scaffold ~/.claude/skills/
```

This allows you to:
- Pull team updates via Git
- Maintain personal customizations separately

---

## Configuration

### Customizing for Your Workflow

After installation, you can customize:

1. **Interview questions** (edit `SKILL.md`):
   - Add Flexport-specific questions
   - Adjust epic structure suggestions
   - Modify success metric categories

2. **PRD patterns** (edit `resources/prd_patterns.md`):
   - Add team terminology
   - Update AC formats
   - Include team-specific examples

3. **Quick reference** (edit `resources/quick_reference.md`):
   - Add team conventions
   - Include links to internal resources

### Sharing Customizations

If you make improvements:

1. **For Flexport PMs:** Submit a PR to the shared repo
2. **Personal:** Keep in your forked version

---

## Getting Help

### Installation Issues

1. Check this troubleshooting guide
2. Ask in #product-management Slack
3. Contact John Peterson directly
4. Open a GitHub issue (if repo is public)

### Usage Questions

1. Review `resources/quick_reference.md`
2. Check main `README.md`
3. Ask during skill execution (it's conversational!)
4. Post in #product-management

---

## Next Steps

Once installed:

1. **Read the Quick Start** in main README.md
2. **Try a test run** with `/pm:prd-scaffold`
3. **Review examples** in `examples/` directory
4. **Use on real project** and gather feedback

---

**Installation complete!** Run `/pm:prd-scaffold` to get started.
