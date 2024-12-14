# Variables
TARGET = README.md
SOURCE = guessinggame.sh

# Default target
all: $(TARGET)

# Rule to generate README.md
$(TARGET): $(SOURCE)
	echo "# Guessing Game Project" > $(TARGET)
	echo "\nCe fichier a été généré le : $$(date)" >> $(TARGET)
	echo "\nNombre de lignes de code dans guessinggame.sh : $$(wc -l < $(SOURCE))" >> $(TARGET)

# Clean rule
clean:
	rm -f $(TARGET)
