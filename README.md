# XSS WAF Bypass using Location Concatenation

### Author: Pushkar Upadhyay
- Email: thepushkar24@gmail.com
- GitHub: [Pushkarup](https://github.com/Pushkarup)
- LinkedIn: [Pushkar Upadhyay](https://www.linkedin.com/in/pushkar-upadhyay-24p/)


## Payload

```html
"><BODy onbeforescriptexecute="x1='cookie';c=')';b='a';location='jav'+b+'script:con'+'fir\u006d('+'document'+'.'+x1+c)">
```

## Payload Description
The payload you provided is an example of an XSS (Cross-Site Scripting) attack. It attempts to bypass a WAF (Web Application Firewall) by using concatenation in the `location` attribute.

## Payload Explanation
The payload starts with a quote `">` to close any open HTML attribute and the opening tag. Then, it sets the `onbeforescriptexecute` event to trigger the following JavaScript code.
The JavaScript code starts by defining variables `x1`, `c`, and `b`. `x1` is set to `'cookie'`, `c` is set to `')'`, and `b` is set to `'a'`. These variables are used to construct the payload.
The payload then sets the `location` to a concatenated string. It uses `'jav' + b + 'script:con' + 'fir\u006d(' + 'document' + '.' + x1 + c'`. This concatenation builds a JavaScript code that executes the `confirm` function with the `document.cookie` as an argument.

## How the Payload Works
By setting the `location` attribute to a JavaScript code, the payload attempts to execute the code when the `onbeforescriptexecute` event is triggered. In this case, it executes the `confirm` function with the `document.cookie` as an argument.
The payload uses concatenation to evade the WAF's detection. By splitting the payload into multiple strings and then concatenating them, it can bypass certain security filters that may be looking for specific keywords or patterns.

## Security Implications
If successful, the payload can execute arbitrary JavaScript code on the victim's browser. In this case, it attempts to retrieve the user's cookies using the `document.cookie` property and displays it in a confirmation dialog.

This type of XSS attack can lead to various security risks, including session hijacking, data theft, and unauthorized actions on behalf of the user.

## Note 
It is important to note that using this payload or any other hacking techniques without proper authorization is illegal and unethical. This documentation is provided for educational purposes only.

