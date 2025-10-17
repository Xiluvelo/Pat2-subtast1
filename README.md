#include <iostream>
#include <string>
#include <map>
#include <cctype> // for toupper()
#include <algorithm> // for transform

using namespace std;

// Function to initialize Morse code mapping
map<char, string> initializeMorseCode() {
    map<char, string> morseCode;
    morseCode['A'] = ".-";
    morseCode['B'] = "-...";
    morseCode['C'] = "-.-.";
    morseCode['D'] = "-..";
    morseCode['E'] = ".";
    morseCode['F'] = "..-.";
    morseCode['G'] = "--.";
    morseCode['H'] = "....";
    morseCode['I'] = "..";
    morseCode['J'] = ".---";
    morseCode['K'] = "-.-";
    morseCode['L'] = ".-..";
    morseCode['M'] = "--";
    morseCode['N'] = "-.";
    morseCode['O'] = "---";
    morseCode['P'] = ".--.";
    morseCode['Q'] = "--.-";
    morseCode['R'] = ".-.";
    morseCode['S'] = "...";
    morseCode['T'] = "-";
    morseCode['U'] = "..-";
    morseCode['V'] = "...-";
    morseCode['W'] = ".--";
    morseCode['X'] = "-..-";
    morseCode['Y'] = "-.--";
    morseCode['Z'] = "--..";
    return morseCode;
}

int main() {
    map<char, string> morseCode = initializeMorseCode();
    string inputMessage;
    
    cout << "=== MORSE CODE TRANSLATOR ===" << endl;
    cout << "Enter a message to translate to Morse code: ";
    getline(cin, inputMessage);
    
    // Convert to uppercase
    transform(inputMessage.begin(), inputMessage.end(), inputMessage.begin(), ::toupper);
    
    cout << "\nLETTER BY LETTER TRANSLATION:" << endl;
    cout << "=============================" << endl;
    
    // Display letter by letter translation
    for (char c : inputMessage) {
        if (morseCode.find(c) != morseCode.end()) {
            cout << c << ": " << morseCode[c] << endl;
        }
    }
    
    cout << "\nFULL MESSAGE TRANSLATION:" << endl;
    cout << "=========================" << endl;
    
    // Display full message in Morse code
    for (char c : inputMessage) {
        if (morseCode.find(c) != morseCode.end()) {
            cout << morseCode[c] << " ";
        } else if (c == ' ') {
            cout << "  "; // Double space for word separation
        }
        // Ignore numbers and other characters as per instructions
    }
    
    cout << "\n\n--- End of Translation ---" << endl;
    
    return 0;
}
