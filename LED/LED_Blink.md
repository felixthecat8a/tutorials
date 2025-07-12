# Controlling an LED with Arduino & Node.js
<!-- Arduino & Arduino IDE -->
## Arduino & Arduino IDE
[***Arduino***](https://www.arduino.cc/) is an open-source electronics platform that consists of both hardware and software components. Arduino includes a series of microcontroller boards that are equipped with various input and output pins. The [*Arduino IDE*](https://www.arduino.cc/en/software/) is a programming environment used to write, compile, and upload code to the Arduino board. It uses a programming language based on C/C++ code to write sketches. Arduino *Sketches* are the program files with the `.ino` extension that contain Arduino code.
<!-- Tinkercad -->
[ ***Tinkercad***](https://www.tinkercad.com/) is an online platform that allows users to design and simulate 3D models. Tinkercad can be used to program and simulate a virtual Arduino microcontroller circuit online. Tinkercad includes a circuit simulation feature that allows users to design and simulate electronic circuits.

## Controlling an LED with Arduino

### Build the Circuit

Build the circuit shown using an Arduino board, a breadboard, an LED, a 220Ω resistor, and a pushbutton.

#### Using Tinkercad:
- If using Tinkercad, click on "Create" and select "Circuit" from the drop-down menu.
- This will open a new workspace so that you can drag-and-drop the components needed.

[Arduino LED & Pushbutton Circuit]()

### Creating a Sketch
Open the Arduino IDE and insert the code that is shown to a new sketch.

#### Using Tinkercad:
- If using Tinkercad, click on "Code" button on the top right area of the screen.
- Change the Edit Mode from "Blocks" to "Text" by clicking on the selector.

```ino
/* ledToggle.ino */
const int ledPin = 13;
const int buttonPin = 10;
int ledState = LOW;
int currentState, lastState;

void setup() {
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin, INPUT_PULLUP);
    currentState = digitalRead(buttonPin);
}
void loop() {
    lastState = currentState;
    currentState = digitalRead(buttonPin);
    if (lastState == HIGH && currentState == LOW){
        ledState = !ledState;
        digitalWrite(ledPin, ledState);
    }
    delay(100);
}
```

### Uploading the Sketch to the Board
1. Open the Arduino IDE and connect your Arduino Uno board to the USB port.
2. Go to **Tools > Board > Arduino Uno** to select the board.
3. Go to **Tools > Port > COM#:Arduino Uno** to select the port.
4. Go to **Sketch > Verify/Compile** or click the checkmark button to compile the sketch.
5. If there are any errors, review the code, fix the errors and compile the code again.
6. Go to **Sketch > Upload** or click the arrow button to upload the sketch.
#### Using Tinkercad:
- If using Tinkercad, click on *"Start Simulation"* button on the top right area of the screen.
- If the code has any errors, the code will not run and the errors will be highlighted in red.

## VC Code & Node.js
[***Visual Studio Code***](https://code.visualstudio.com/) is a source-code editor made by Microsoft. PowerShell is a task-based command-line shell and scripting language created by Microsoft that is available in the VS Code editor. For this project, we will be using VS Code with Node.js installed on the computer. When you open VS Code, it displays a code editor window, a command terminal and a file explorer.

[***Node.js***](https://nodejs.org/) is an open-source, server-side JavaScript runtime environment built on the Chrome V8 JavaScript engine. Node Package Manager, NPM, comes bundled with the Node.js installation. NPM is a package manager used for managing and distributing open-source JavaScript packages and libraries. An alternative to NPM is Yarn. ***Yarn*** is a package manager developed by Facebook in collaboration with other companies and the open-source community to address some limitations of existing package managers.
<!-- Yarn Package Manager -->
Install Yarn via NPM:
```ps
npm install --global yarn
```
### Johnny-Five & SerialPort
[***Johnny-Five***](https://johnny-five.io/) is an open-source JavaScript framework that allows you to control and interact with various hardware devices using JavaScript. [***SerialPort***](https://serialport.io/) is a JavaScript library that provides a simple and convenient API for serial communication. It allows you to read from and write to serial ports on your computer or embedded devices.

## Controlling an LED with JavaScript using Johnny-Five

#### Create a new project directory with a JavaScript file in it named "ledToggle.js".
```ps
New-Item -Path .\Project -ItemType Directory
New-Item -Path .\Project\ledToggle.js -ItemType File
```
Enter the project directory & initiate a project.
```ps
cd Project
yarn init -y
```
Adding `--yes` or `-y` to the command bypasses the prompt questions. A *package.json* file will be generated in the Project directory.
If using NPM, the command is `npm init --yes`.
- Hint: cd.. will return you to a parent directory.
- Hint: cd 'My Project' will let you enter a directory with a space in the title.
- Hint: cd E:\ will change the directory to the E drive for access to a USB drive.

#### Install the necessary packages.

- Install the Johnny-Five and SerialPort packages.
```shell
yarn add johnny-five serialport
```
or
```shell
npm install johnny-five serialport
```
Installing packages creates a `package.json` file and a `yarn.lock` or `package-lock.json` file
The file directory should look like the file directory map shown.

```
  Project/
  ├── node_modules/
  ├── ledToggle.js
  ├── package.json
  └── yarn.lock or package-lock.json
```
