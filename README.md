# pat2-subtask1
#Morse Code Overview

Morse code is a method of communication that uses dots (.) and dashes (-) to represent letters and numbers. It is used to send messages over long distances using sound, light, or signals.

#History of Morse Code

Morse code was developed in the 1830s and 1840s by Samuel Morse and Alfred Vail. It was mainly used with the telegraph system to send messages quickly over long distances.

#How Morse Code Works
Morse code represents each letter using:
Dots (.) → short signals
Dashes (-) → long signals

#Example:
A = .-
B = -...                              C = -.-.                            Words are formed by combining these signals.

#References
https://en.wikipedia.org/wiki/Morse_code⁠
https://www.britannica.com/topic/Morse-Code


⁠
#include <iostream>
#include <map>
#include <string>
#include <cctype>
using namespace std;

int main() {
    map<char, string> morse = {
        {'A', ".-"},   {'B', "-..."}, {'C', "-.-."}, {'D', "-.."},
        {'E', "."},    {'F', "..-."}, {'G', "--."},  {'H', "...."},
        {'I', ".."},   {'J', ".---"}, {'K', "-.-"},  {'L', ".-.."},
        {'M', "--"},   {'N', "-."},   {'O', "---"},  {'P', ".--."},
        {'Q', "--.-"}, {'R', ".-."},  {'S', "..."},  {'T', "-"},
        {'U', "..-"},  {'V', "...-"}, {'W', ".--"},  {'X', "-..-"},
        {'Y', "-.--"}, {'Z', "--.."}
    };

    string message;
    cout << "Enter a short message: ";
    getline(cin, message);

    string fullMorse = "";

    for (char c : message) {
        if (isalpha(c)) {
            char upper = toupper(c);
            cout << upper << ": " << morse[upper] << endl;
            fullMorse += morse[upper] + "   "; // 3 spaces between letters
        }
    }

    cout << "\nFull Morse code with spaces:\n" << fullMorse << endl;

    return 0;
}
