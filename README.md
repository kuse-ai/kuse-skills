# Kuse AI Skills

Professional AI-powered skills for content creation, web design, and business optimization. This collection extends Claude's capabilities with specialized workflows and domain expertise.

## 🚀 Available Skills

### Content Skills

#### [Ken Style Social Media](./ken-style-social-media)
Create authentic social media content in Ken's distinctive multilingual style, mixing Cantonese, English, and Traditional Chinese for maximum engagement and conversion.

**Use Cases:**
- Personal brand building posts
- Product showcase content
- Educational content sharing
- Viral social media campaigns

#### [Content Optimization](./content-optimization)
Optimize content for SEO, engagement, and conversion across multiple platforms with comprehensive analysis and actionable recommendations.

**Use Cases:**
- Blog post SEO optimization
- Landing page copy improvement
- Email marketing enhancement
- Content strategy development

### Design Skills

#### [Modern Web Design](./modern-web-design)
Create beautiful, responsive websites using modern design principles, Tailwind CSS, and contemporary UI patterns.

**Use Cases:**
- Landing pages and marketing sites
- Portfolio and business websites
- SaaS application interfaces
- E-commerce product pages

## 📦 Installation

### Claude Code Plugin Installation

1. **Download the Plugin**
   ```bash
   git clone https://github.com/kuse-ai/kuse-skills.git
   cd kuse-skills
   ```

2. **Install as Claude Code Plugin**
   ```bash
   # Copy to Claude Code plugins directory
   cp -r . ~/.claude/plugins/kuse-ai-skills/
   ```

3. **Restart Claude Code**
   The skills will be automatically available in your next Claude Code session.

### Individual Skill Installation

You can also install individual skills to your project or personal skills directory:

```bash
# For project-specific skills
mkdir -p .claude/skills
cp -r ken-style-social-media .claude/skills/

# For personal skills (available across all projects)
mkdir -p ~/.claude/skills
cp -r modern-web-design ~/.claude/skills/
```

## 🎯 How to Use

Skills are automatically invoked by Claude when your request matches the skill's description. Simply ask for what you need:

### Content Creation Examples
```
"Generate a ken-style social media post about our new AI tool launch"
"Optimize this blog post for SEO and engagement"
"Create a landing page for our SaaS product"
```

### Design Examples
```
"Build a modern portfolio website with dark theme"
"Create a professional business landing page"
"Design a responsive e-commerce product page"
```

### Optimization Examples
```
"Analyze this content for SEO improvements"
"Optimize this landing page for conversions"
"Review this blog post for readability and engagement"
```

## 🛠 Skill Categories

### Content Skills
Focus on creating, optimizing, and enhancing written content across platforms:
- **Social Media**: Platform-specific content creation and optimization
- **SEO Content**: Search engine optimized blog posts and articles
- **Marketing Copy**: Conversion-focused sales and marketing materials
- **Brand Voice**: Consistent messaging and tone development

### Design Skills
Create modern, responsive web experiences:
- **Website Design**: Complete website creation with modern frameworks
- **UI Components**: Reusable interface elements and patterns
- **Responsive Design**: Mobile-first, cross-device optimization
- **Design Systems**: Consistent visual language and branding

## 📚 Documentation

Each skill includes comprehensive documentation:
- **SKILL.md**: Main skill instructions and usage guidelines
- **references/**: Detailed guides, templates, and best practices
- **assets/**: Reusable templates, components, and resources
- **scripts/**: Automation tools and utilities (where applicable)

## 🔧 Development

### Creating Custom Skills

Use the included skill creation framework to build your own:

1. **Initialize New Skill**
   ```bash
   mkdir my-custom-skill
   cd my-custom-skill
   ```

2. **Create SKILL.md**
   ```yaml
   ---
   name: my-custom-skill
   description: Brief description of what this skill does and when to use it
   ---

   # Skill instructions and workflow
   ```

3. **Add Resources**
   - `references/`: Documentation and guides
   - `assets/`: Templates and reusable files
   - `scripts/`: Automation tools

### Contributing

We welcome contributions! Please:

1. Fork this repository
2. Create a feature branch
3. Follow the skill creation guidelines
4. Submit a pull request with detailed description

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Support

- **Issues**: [GitHub Issues](https://github.com/kuse-ai/kuse-skills/issues)
- **Discussions**: [GitHub Discussions](https://github.com/kuse-ai/kuse-skills/discussions)
- **Email**: support@kuse.ai

## 🎉 Acknowledgments

- Built for [Claude Code](https://claude.com/code) by Anthropic
- Inspired by the open-source skills community
- Special thanks to all contributors and beta testers

---

**Made with ❤️ by [Kuse AI](https://kuse.ai)**