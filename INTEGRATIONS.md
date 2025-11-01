# Integration Points and External Dependencies

This document lists and explains all integration points with external systems, APIs, services, and libraries used in the Bohdan-AI/.github repository.

## Table of Contents
- [Profile Integrations](#profile-integrations)
- [CI/CD Integrations](#cicd-integrations)
- [Configuration](#configuration)
- [Setup Instructions](#setup-instructions)

---

## Profile Integrations

### 1. README Typing SVG (readme-typing-svg.herokuapp.com)

**Purpose**: Generates dynamic typing animation SVG for the GitHub profile README.

**Location**: `/profile/README.md`

**Usage**:
```markdown
<img src="https://readme-typing-svg.herokuapp.com/?lines=Welcome+to+bohdan.AI+👋;Keep+In+Touch+with+bohdan.AI;Secure+AI+Solutions+Expert;Enterprise+Security+Expert&center=true&width=380&height=45&color=00FFFF&vCenter=true&size=24">
```

**Configuration Parameters**:
- `lines`: Text lines to display (separated by semicolons)
- `center`: Center alignment (true/false)
- `width`: Width in pixels (380)
- `height`: Height in pixels (45)
- `color`: Text color in hex (00FFFF - cyan)
- `vCenter`: Vertical center alignment (true/false)
- `size`: Font size (24)

**Documentation**: [https://github.com/DenverCoder1/readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg)

**Setup**: No authentication required. Simply use the URL with query parameters in markdown.

---

### 2. Shields.io (img.shields.io)

**Purpose**: Generates custom badges for profile enhancement and status display.

**Location**: `/profile/README.md`

**Usage Examples**:

**Custom Badge**:
```markdown
![bohdan.AI](https://img.shields.io/badge/bohdan.AI-Enterprise-00FFFF?style=for-the-badge)
```

**LinkedIn Follower Badge** (Note: Follower count is hardcoded in badge and should be updated periodically):
```markdown
![LinkedIn](https://img.shields.io/badge/12.9K_Followers-0A66C2?style=flat&logo=linkedin&logoColor=white)
```

**Book Badge**:
```markdown
![Book](https://img.shields.io/badge/AI_Navigating-FF4500?style=flat&logo=amazon&logoColor=white)
```

**Configuration Parameters**:
- Badge format: `/{label}-{message}-{color}`
- `style`: Badge style (flat, for-the-badge, plastic, flat-square)
- `logo`: Logo name from Simple Icons
- `logoColor`: Logo color (white, hex values)
- `color`: Badge color (hex values or named colors)

**Documentation**: [https://shields.io/](https://shields.io/)

**Setup**: No authentication required. URL-based badge generation.

---

### 3. Komarev Profile Views Counter (komarev.com/ghpvc)

**Purpose**: Tracks and displays profile view statistics.

**Location**: `/profile/README.md`

**Usage**:
```markdown
[![Visits](https://komarev.com/ghpvc/?username=bohdanaims&label=Profile%20views&color=0e75b6&style=flat)](https://bohdan.ai)
```

**Configuration Parameters**:
- `username`: GitHub username (bohdanaims)
- `label`: Display label (Profile views)
- `color`: Badge color in hex (0e75b6 - blue)
- `style`: Badge style (flat, flat-square, plastic)

**Documentation**: [https://github.com/antonkomarev/github-profile-views-counter](https://github.com/antonkomarev/github-profile-views-counter)

**Setup**: No authentication required. Counter automatically tracks views when badge is displayed.

---

### 4. LinkedIn Integration

**Purpose**: Professional networking and follower engagement.

**Location**: `/profile/README.md`

**Usage**:
```markdown
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/comm/mynetwork/discovery-see-all?usecase=PEOPLE_FOLLOWS&followMember=bohdanai)
```

**Links**:
- Profile follow link: `https://www.linkedin.com/comm/mynetwork/discovery-see-all?usecase=PEOPLE_FOLLOWS&followMember=bohdanai`

**Configuration**: 
- Username/handle: `bohdanai`
- Profile action: Follow member
- Metrics displayed: 12.9K Followers (as of profile snapshot - update badge manually as needed)

**Documentation**: [LinkedIn Profile URL Structure](https://www.linkedin.com/help/linkedin)

**Setup**: Ensure LinkedIn profile is public for follower stats to be visible.

---

### 5. Calendly Integration

**Purpose**: Meeting scheduling and calendar management.

**Location**: `/profile/README.md`

**Usage**:
```markdown
[![Book a Meeting](https://img.shields.io/badge/Book_a_Meeting-006BFF?style=for-the-badge&logo=calendly&logoColor=white)](https://calendly.com/bohdanlukianets)
```

**Configuration**:
- Calendly username: `bohdanlukianets`
- Booking URL: `https://calendly.com/bohdanlukianets`

**Documentation**: [https://help.calendly.com/](https://help.calendly.com/)

**Setup Instructions**:
1. Create a Calendly account at [calendly.com](https://calendly.com)
2. Configure meeting types and availability
3. Set up calendar integration (Google Calendar, Outlook, etc.)
4. Use the personal booking link in profile

---

### 6. Amazon Author Central

**Purpose**: Book publication and sales tracking.

**Location**: `/profile/README.md`

**Usage**:
```markdown
[![Book](https://img.shields.io/badge/AI_Navigating-FF4500?style=flat&logo=amazon&logoColor=white)](https://amazon.com/dp/B0D22DY2J8)
```

**Configuration**:
- Book ASIN: `B0D22DY2J8`
- Product URL: `https://amazon.com/dp/B0D22DY2J8`
- Book Title: "AI Navigating—Fundamentals of Machine Learning"

**Documentation**: [Amazon Kindle Direct Publishing](https://kdp.amazon.com/)

**Setup**: Book must be published through Amazon KDP or similar service to obtain ASIN.

---

### 7. bohdan.ai Website

**Purpose**: Personal/professional website for enterprise services.

**Location**: `/profile/README.md`

**Usage**:
- Primary domain: `https://bohdan.ai`
- Contact email: `help@bohdan.ai`

**Configuration**: Custom domain serving as homepage and contact point.

**Setup**: Domain registration and website hosting required. Email forwarding configured for contact address.

---

## CI/CD Integrations

### 8. Azure Pipelines

**Purpose**: Continuous Integration and Continuous Deployment automation.

**Location**: `/azure-pipelines.yml`

**Configuration**:
```yaml
trigger:
- main-1

pool:
  vmImage: ubuntu-latest

steps:
- script: echo Hello, world!
  displayName: 'Run a one-line script'

- script: |
    echo Add other tasks to build, test, and deploy your project.
    echo See https://aka.ms/yaml
  displayName: 'Run a multi-line script'
```

**Key Settings**:
- **Trigger Branch**: `main-1` (Note: This is the configured branch name; typical repositories use `main`)
- **VM Image**: `ubuntu-latest`
- **Pipeline Type**: YAML-based

**Documentation**: [https://aka.ms/yaml](https://aka.ms/yaml)

**Setup Instructions**:
1. Create an Azure DevOps account at [dev.azure.com](https://dev.azure.com)
2. Create a new project
3. Connect GitHub repository to Azure Pipelines
4. Configure service connection with GitHub OAuth
5. Set up pipeline using existing `azure-pipelines.yml`
6. Configure branch policies and triggers as needed

**Required Permissions**:
- Azure DevOps project access
- GitHub repository webhook permissions
- Service connection credentials

**Environment Variables**: Currently none configured in the pipeline file.

---

## Configuration Files

### azure-pipelines.yml
- **Location**: `/azure-pipelines.yml`
- **Purpose**: Azure Pipelines CI/CD configuration
- **Format**: YAML

### profile/README.md
- **Location**: `/profile/README.md`
- **Purpose**: GitHub organization profile page
- **Format**: Markdown with embedded HTML

---

## Environment Variables

Currently, no environment variables are explicitly required for the integrations in this repository. All integrations use:
- Public APIs without authentication
- Direct URL-based services
- Static configuration in markdown files

**Future Considerations**:
If adding authenticated services, consider using:
- GitHub Secrets for sensitive data
- Azure Key Vault for Azure Pipeline secrets
- Environment-specific configuration files

---

## Setup Instructions

### Initial Repository Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Bohdan-AI/.github.git
   cd .github
   ```

2. **Profile Page Setup**:
   - The `profile/README.md` automatically displays on the organization's GitHub profile
   - No additional configuration needed
   - Updates to this file reflect immediately on the profile

3. **Azure Pipelines Setup**:
   - Follow the Azure Pipelines setup instructions above
   - Modify `azure-pipelines.yml` as needed for your CI/CD requirements
   - Update trigger branch if needed (currently set to `main-1`)

### Updating Integration Services

#### To Update Profile Badges:
1. Edit `/profile/README.md`
2. Modify URL parameters for services (Shields.io, Typing SVG, etc.)
3. Commit and push changes

#### To Update Azure Pipeline:
1. Edit `/azure-pipelines.yml`
2. Add build, test, or deployment steps
3. Commit and push changes
4. Pipeline runs automatically on trigger branch

---

## Additional Resources

- **GitHub Special Repository**: [Creating an organization README](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/customizing-your-organizations-profile)
- **Azure DevOps Documentation**: [Azure Pipelines Documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/)
- **GitHub OAuth Apps**: [Creating an OAuth App](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app)

---

## Notes on OAuth Integration

The issue includes a reference image showing OAuth app registration. While no OAuth implementation is currently present in this repository, here's how to integrate GitHub OAuth:

### GitHub OAuth App Setup

**Purpose**: Authenticate users with GitHub credentials

**Registration Steps**:
1. Go to GitHub Settings → Developer settings → OAuth Apps
2. Click "New OAuth App"
3. Fill in required fields:
   - **Application name**: User-facing name
   - **Homepage URL**: Full URL to application homepage
   - **Application description**: Optional description
   - **Authorization callback URL**: OAuth redirect URL

**Configuration After Registration**:
- Save Client ID (public)
- Save Client Secret (private - store securely)
- Never commit secrets to repository

**Documentation**: [GitHub OAuth Documentation](https://docs.github.com/en/developers/apps/building-oauth-apps)

**Implementation**: Would require adding OAuth flow to application code with proper environment variable management for credentials.

---

## Support and Contact

For questions about integrations or setup:
- **Email**: help@bohdan.ai
- **Website**: [bohdan.ai](https://bohdan.ai)
- **Book Meeting**: [Calendly](https://calendly.com/bohdanlukianets)
