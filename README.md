let strs = [];
let i = 0;
let deleteFlag = false;
let s = 0;
let offset = 50;
let mainFontSize = 60;
let secondaryFontSize = 40;

function setup() {
   createCanvas(1920, 1080);
  frameRate(30);
  textAlign(CENTER);
  textSize(40);
  fill(0);

  // Agregar tus cadenas al array "strs"
  strs.push(["Hey there!", "My name is Lionel Juárez."]);
  strs.push(["I'm a student of a higher technical degree in multiplatform application developer, as well as self-taught.", "I'm currently carrying out a personal project for a mobile application, developing it in Java"]);
  strs.push(["I've been learning to code for 2 years.", "I'm fluent in Java, C++, Python, Swift, JavaScript, and HTML & CSS."]);
  strs.push(["I've created apps and websites using what I've learned.", "Right now you can't find the source code for my projects, but you will soon!"]);
  strs.push(["Feel free to reach out to say hi!", ""]);

}

function draw() {
  background(255);

  if (s < strs.length) {
    if ((strs[s][0].length >= i || strs[s][1].length >= i) && !deleteFlag) {
      if (strs[s][0].length >= i) {
        textSize(mainFontSize);
        text(strs[s][0].substring(0, i), width / 2, height / 2 - offset);
      } else {
        textSize(mainFontSize);
        text(strs[s][0], width / 2, height / 2 - offset);
      }
      if (strs[s][1].length >= i) {
        textSize(secondaryFontSize);
        text(strs[s][1].substring(0, i), width / 2, height / 2 + offset);
      } else {
        textSize(secondaryFontSize);
        text(strs[s][1], width / 2, height / 2 + offset);
      }
      i++;
    } else {
      if (!deleteFlag) {
        delay(1500);
      }
      deleteFlag = true;
    }

    if (deleteFlag) {
      if (i > 0) {
        if (i < strs[s][0].length) {
          textSize(mainFontSize);
          text(strs[s][0].substring(0, i - 1), width / 2, height / 2 - offset);
        } else {
          textSize(mainFontSize);
          text(strs[s][0], width / 2, height / 2 - offset);
        }
        if (i < strs[s][1].length) {
          textSize(secondaryFontSize);
          text(strs[s][1].substring(0, i - 1), width / 2, height / 2 + offset);
        } else {
          textSize(secondaryFontSize);
          text(strs[s][1], width / 2, height / 2 + offset);
        }
        i--;
      } else {
        deleteFlag = false;
        s++;
      }
    }
  }
}
