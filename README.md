
def generate_exact_readme():
    # Data meticulously extracted from ej_website_final_no_grytte.html
    user_info = {
        "name": "EJ Matejevich",
        "tagline": "Creator · Innovator · Developer",
        "intro": "Born and raised in NYC with Serbian, Irish, and Filipino roots. A five-year student at The Browning School driven by a passion for finance, entrepreneurship, law, and technology — committed to growth in every arena.",
        "education": "The Browning School",
        "location": "New York City, NY",
        "contact": {
            "email": "ematejevich@browning.edu",
            "phone": "(917) 494-6038",
            "location": "New York City, NY"
        },
        "stats": [
            {"label": "Academic Tenure", "value": "5 years at The Browning School"},
            {"label": "Core Focus", "value": "Finance, Law, & Technology"},
            {"label": "Identity", "value": "Serbian, Irish, and Filipino Heritage"}
        ],
        "activities": [
            {
                "name": "The Grytte Newspaper",
                "role": "Contributor",
                "details": [
                    "Active involvement in school journalism and reporting.",
                    "Contributing to the long-standing publication at The Browning School."
                ]
            },
            {
                "name": "Entrepreneurship & Innovation",
                "role": "Student Innovator",
                "details": [
                    "Focusing on the intersection of modern finance and emerging tech.",
                    "Applying problem-solving skills to real-world entrepreneurial challenges."
                ]
            }
        ],
        "skills": {
            "Technical & Innovation": [
                "Web Development", 
                "Technical Problem Solving", 
                "Innovation"
            ],
            "Mindset & Professional": [
                "Entrepreneurial mindset", 
                "Adaptability & problem solving", 
                "Critical Thinking"
            ],
            "Communication & Leadership": [
                "Public Speaking", 
                "Leadership", 
                "Journalism"
            ]
        }
    }

    # Constructing the exact replica in Markdown format
    md = []
    md.append(f"# {user_info['name']}")
    md.append(f"### {user_info['tagline']}\n")
    md.append(f"> {user_info['intro']}\n")
    
    md.append("---")
    
    md.append("## 🎓 Education & Background")
    md.append(f"- **School:** {user_info['education']}")
    md.append(f"- **Location:** {user_info['location']}")
    md.append(f"- **Heritage:** {user_info['stats'][2]['value']}")
    
    md.append("\n## 📊 Personal Highlights")
    md.append("| Category | Detail |")
    md.append("| :--- | :--- |")
    for stat in user_info['stats']:
        md.append(f"| {stat['label']} | {stat['value']} |")

    md.append("\n## 🛠 Skills & Competencies")
    for category, skills in user_info['skills'].items():
        md.append(f"#### {category}")
        md.append(", ".join([f"`{s}`" for s in skills]) + "")

    md.append("\n## 🚀 Activities & Involvement")
    for act in user_info['activities']:
        md.append(f"### {act['name']}")
        md.append(f"*{act['role']}*")
        for detail in act['details']:
            md.append(f"- {detail}")

    md.append("\n## 📫 Get in Touch")
    md.append(f"- **Email:** [{user_info['contact']['email']}](mailto:{user_info['contact']['email']})")
    md.append(f"- **Phone:** {user_info['contact']['phone']}")
    md.append(f"- **Location:** {user_info['contact']['location']}")

    md.append("\n---\n<p align='center'><i>\"Committed to growth in every arena.\"</i></p>")

    # File Creation Logic
    file_path = "README.md"
    try:
        with open(file_path, "w", encoding="utf-8") as f:
            f.write("\n".join(md))
        print(f"Successfully generated {file_path} as a full replica of your website data.")
    except Exception as e:
        print(f"An error occurred while writing the file: {e}")

if __name__ == "__main__":
    generate_exact_readme()
