##C++


#include <iostream>
#include <vector>
#include <string>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    // Lista de palabras a adivinar
    vector<string> palabras;
    palabras.push_back("messi");
    palabras.push_back("modric");
    palabras.push_back("casillas");
    palabras.push_back("ronaldhino");
    palabras.push_back("zidane");
    palabras.push_back("ronaldo");
    palabras.push_back("vinicius");
    palabras.push_back("kroos");
    palabras.push_back("cuortois");
    palabras.push_back("xavi");
    palabras.push_back("lewandowski");
    palabras.push_back("neur");
    
    // N�mero de intentos permitidos
    int intentos = 6;

    // Generar una semilla aleatoria
    srand(time(0));

    // Seleccionar una palabra aleatoria de la lista
    string palabra = palabras[rand() % palabras.size()];

    // Crear la palabra secreta con guiones bajos
    string acertar(palabra.length(), '_');

    cout << "!Ahorcado adivina la palabra!" << endl;

    // El ciclo while se utiliza para los intentos restantes que tenga el usuario
    while (intentos > 0 && acertar != palabra) {
        cout << "Palabra a adivinar: " << acertar << endl;
        char letra;
        cout << "Ingresa una letra: ";
        cin >> letra;

        // Aqu� se verificar� si el usuario pone o no la letra correcta
        bool acierto = false;
        for (int i = 0; i < palabra.length(); i++) {
            if (palabra[i] == letra) {
                acertar[i] = letra;
                acierto = true;
            }
        }

        if (acierto) {
            cout << "Acertaste!" << endl;
        } else {
            cout << "Fallaste!" << endl;
            intentos--;
        }

        cout << "Intentos restantes: " << intentos << endl;
    }

    // Si el usuario acierta la palabra, saldr� como ganador
    if (acertar == palabra) {
        cout << "�Ganaste! �Buena esa!" << endl;
    } else {
        cout << "�Perdedor! La palabra era: " << palabra << endl;
    }

    return 0;
}

##Pythom

#import ramdon lo utilizaremos para generar numeros aleatorios y elegir las palabras en un listado
import random

#lista que contendra las palabras a adivinar y el numero de intentos que se le quiera dar al usuario
palabras = ["messi", "modric", "casillas","ronaldhino","zidane","ronaldo","vinicius","kroos","cuortois","xavi","lewandowski","neur"]
intentos = 6

# Seleccionar una palabra aleatoria de la lista anterior
palabra = random.choice(palabras)

# Crear la palabra secreta con guion bajo
acertar = "_" * len(palabra)

print("!Ahorcado acierta la palabra!")

#el ciclo while se usara para los intentos restantas que tenga el usuario
while intentos > 0 and acertar != palabra:
    print("Palabra a adivinar:", acertar)
    letra = input("Ingresa una letra: ")
    
    #aca se verificara si el usuario pone o no la letra correcta y se le restara un intento si falla o sumara una nueva letra si acierta
    if letra in palabra:
        print("Acertaste!")
        acertar = "".join(letra if letra == letra_palabra else acertar[i] for i, letra_palabra in enumerate(palabra))
    else:
        print("Fallaste!")
        intentos -= 1
    
    print("Intentos restantes:", intentos)

#si el usuario acierta la palabra saldra ganador pero si la falla saldra perdedor y cual era la palabra correcta
if acertar == palabra:
    print("Ganaste buena esa!")
else:
    print("Perdedor! La palabra era:", palabra)

    
