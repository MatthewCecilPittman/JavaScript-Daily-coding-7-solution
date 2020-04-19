# JavaScript-Daily-coding-7-solution
function numDecodingsRHelper(message, index) {
  if (index === message.length) return 1;
  if (message.charAt(index) === '0') return 0;

  // Single Number
  let totalDecodings = numDecodingsRHelper(message, index + 1);
  if (index < message.length - 1) {
    // Double Number
    const doubleNum = parseInt(message.substring(index, index + 2), 10);

    if (doubleNum >= 10 && doubleNum <= 26)
      totalDecodings += numDecodingsRHelper(message, index + 2);
  }
  return totalDecodings;
} 
