<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hacker Terminal</title>
  <style>
    body {
      background-color: black;
      color: limegreen;
      font-family: 'Courier New', monospace;
      padding: 20px;
    }
    #terminal {
      white-space: pre-wrap;
    }
    .cursor {
      display: inline-block;
      animation: blink 1s step-end infinite;
    }
    @keyframes blink {
      from, to { color: transparent; }
      50% { color: limegreen; }
    }
  </style>
</head>
<body>
  <div id="terminal"></div>
  <script>
    const terminal = document.getElementById('terminal');
    const lines = [
      'Connecting to 192.168.0.12...',
      'Bypassing firewall...',
      'Accessing secure server...',
      'Downloading encrypted passwords...',
      'Decrypting...',
      'Access granted ✅',
      'User: admin',
      'Password: ********',
      'Launching backdoor...',
      'System hacked! 😈'
    ];

    let line = 0;
    let char = 0;

    function typeLine() {
      if (line >= lines.length) {
        terminal.innerHTML += '\n\n> All systems compromised.';
        return;
      }
      if (char < lines[line].length) {
        terminal.innerHTML += lines[line][char++];
        setTimeout(typeLine, 50);
      } else {
        terminal.innerHTML += '\n';
        line++;
        char = 0;
        setTimeout(typeLine, 400);
      }
    }

    typeLine();
  </script>
</body>
</html>
