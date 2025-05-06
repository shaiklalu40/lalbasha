from fpdf import FPDF

# Create a class for the PDF layout
class ResumePDF(FPDF):
    def header(self):
        self.set_font("Arial", "B", 14)
        self.set_text_color(0, 102, 204)
        self.cell(0, 10, "SHAIK LALBASHA", ln=True, align="C")
        self.set_font("Arial", "", 11)
        self.set_text_color(0, 0, 0)
        self.cell(0, 10, "+91-7675870091 | shaiklalu40@gmail.com | linkedin.com/in/shaik-lalbasha", ln=True, align="C")
        self.ln(5)

    def section_title(self, title):
        self.set_font("Arial", "B", 12)
        self.set_text_color(0, 51, 102)
        self.cell(0, 10, title, ln=True)
        self.set_text_color(0, 0, 0)

    def section_body(self, body):
        self.set_font("Arial", "", 11)
        self.multi_cell(0, 8, body)
        self.ln(2)

# Create the PDF
pdf = ResumePDF()
pdf.add_page()

# Career Objective
pdf.section_title("🎯 Career Objective")
pdf.section_body("Aspiring Computer Science professional seeking a challenging role in IT to leverage technical skills in Python, Machine Learning, and Web Development, while continuously learning and contributing to organizational growth.")

# Education
pdf.section_title("🎓 Education")
edu = """B.Tech – Computer Science Engineering
Sai Tirumala NVR Engineering College, Andhra Pradesh
2021 – 2025 | CGPA: 7.25

Intermediate – MPC
Sri Saraswathi Junior College, Andhra Pradesh
2019 – 2021 | Percentage: 72%

SSC – 10th Standard
Sri Sai Vidhyanikethan, Andhra Pradesh
2018 – 2019 | GPA: 9.2"""
pdf.section_body(edu)

# Technical Skills
pdf.section_title("💻 Technical Skills")
skills = """Programming Languages: Python (NumPy, Pandas), Java, SQL
Tools & Technologies: MS Excel, Web Development
Domains: Artificial Intelligence, Machine Learning"""
pdf.section_body(skills)

# Certifications
pdf.section_title("📜 Certifications")
certs = """Full Stack Development – Blackbuck | Mar 2025
Introduction to AI-ML – EduSkills | Sep 2023
Web Development Internship – InternPe | Aug–Sep 2024
Intermediate Python Programming – HackerRank | Feb 2024"""
pdf.section_body(certs)

# Projects
pdf.section_title("🛠️ Projects")
projects = """Restaurant Rating Prediction Model (Mar 2025)
- Built an ML model using ensemble techniques (Random Forest) for predicting restaurant ratings.
- Applied data preprocessing, feature engineering, and model evaluation techniques.

Trainee Machine Learning Project (May 2023 – Present)
- Gained hands-on experience with NLP techniques, text preprocessing, and APIs like OpenAI & Hugging Face."""
pdf.section_body(projects)

# Achievements
pdf.section_title("🏆 Achievements")
achievements = """- Elected as Class Representative, facilitating communication and leading initiatives.
- Received 2nd Place Medal for Academic Excellence."""
pdf.section_body(achievements)

# Soft Skills
pdf.section_title("💡 Soft Skills")
pdf.section_body("Problem Solving, Quick Learning, Leadership")

# Languages
pdf.section_title("🌐 Languages")
pdf.section_body("English: Fluent | Telugu: Advanced | Hindi: Intermediate | Urdu: Good")

# Personal Details
pdf.section_title("📌 Personal Details")
details = """Date of Birth: December 16, 2003
Address: D.No. 2-183, Near Post Office, Ch. Upplapadu, Naguluppalapadu Mandal,
Prakasam District, Andhra Pradesh – 523180"""
pdf.section_body(details)

# Save the PDF
output_path = "/mnt/data/Shaik_Lalbasha_Resume.pdf"
pdf.output(output_path)

output_path
