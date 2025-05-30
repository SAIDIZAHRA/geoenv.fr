from PyPDF2 import PdfReader

# Charger le PDF pour en extraire le texte (et les métadonnées des images si possible)
pdf_path = "/mnt/data/essaie site geoen+mentios legales.pdf"
reader = PdfReader(pdf_path)

# Extraire tout le texte de toutes les pages
text_content = ""
for page in reader.pages:
    text_content += page.extract_text() + "\n"

# Nombre de pages
num_pages = len(reader.pages)

text_content[:2000], num_pages  # Afficher un extrait du texte + nombre de pages pour vérification
