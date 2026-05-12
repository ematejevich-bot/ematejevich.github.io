import os

def generate_full_readme():
    # Comprehensive data extracted from all sections of your website
    user_data = {
        "name": "EJ Matejevich",
        "tagline": "Creator · Innovator · Developer",
        "location": "New York City, NY",
        "email": "ematejevich@browning.edu",
        "school": "The Browning School",
        "bio": ("Born and raised in NYC with Serbian, Irish, and Filipino roots. "
                "A five-year student at The Browning School driven by a passion for finance, "
                "entrepreneurship, law, and technology — committed to growth in every arena."),
        
        "highlights": [
            {"label": "Education", "value": "The Browning School"},
            {"label": "Location", "value": "New York City, NY"},
            {"label": "Focus", "value": "Finance & Tech"}
        ],
        
        "activities": [
            {
                "title": "Grytte Newspaper",
                "role": "Lead/Contributor",
                "points": [
                    "Active contributor to school journalism.",
                    "Focused on reporting and content creation."
                ]
            },
            {
                "title": "Entrepreneurship & Innovation",
                "role": "Creator",
                "points": [
                    "Building and scaling modern digital solutions.",
                    "Applying technology to solve financial and legal problems."
                ]
            }
        ],
        
        "skill_categories": {
            "Development & Tech": ["Web Development", "Technical Problem Solving", "Innovation"],
            "Professional": ["Entrepreneurial Mindset", "Adaptability", "Critical Thinking"],
            "Communication": ["Public Speaking", "Leadership", "Journalism"]
        }
    }

    # Constructing the Markdown Content
    content = f"""# Hi there, I'm {user_data['name']} 👋

### {user_data['tagline']}

{user_data['bio']}

---

### 📊 Quick Stats
| Item | Details |
| :--- | :--- |
| 🏫 **School** | {user_data['school']} |
| 📍 **Location** | {user_data['location']} |
| 📧 **Contact** | {user_data['email']} |

---

### 🛠 Skills & Competencies

"""
    # Adding Skills from all categories
    for category, skills in user_data['skill_categories'].items():
        content += f"**{category}:** " + ", ".join(skills) + "\\n\\n"

    content += """---

### 🚀 Key Activities & Projects

"""
    # Adding Activities extracted from your 'Activities' page
    for act in user_data['activities']:
        content += f"#### {act['title']} \\n*{act['role']}*\\n"
        for point in act['points']:
            content += f"- {point}\\n"
        content += "\\n"

    content += """---

### 📫 Connect with Me
- **Email:** ematejevich@browning.edu
- **Location:** New York City, NY

<p align="center">
  <i>"Committed to growth in every arena."</i>
</p>
"""

    # Create the file
    try:
        with open("README.md", "w", encoding="utf-8") as f:
            f.write(content)
        print("Successfully generated a comprehensive README.md based on all website pages!")
    except Exception as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    generate_full_readme()
