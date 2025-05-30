---
layout: "lesson"
lang: "hi"
title: "गणित"
description: "यह पाठ LaTeX के गणित मोड को प्रस्तुत करता है और यह बताता है कि आप इनलाइन तथा डिस्प्ले सूत्र कैसे टाइप कर सकते हैं, amsmath पैकेज द्वारा प्रदान किए गए विस्तार क्या हैं, और गणित में फॉन्ट कैसे बदले जा सकते हैं।"
toc-anchor-text: "गणित"
toc-description: "गणित मोड और गणितीय संकेतन"
---

# गणित

<span
  class="summary">यह पाठ LaTeX के गणित मोड को प्रस्तुत करता है और यह बताता है कि आप इनलाइन (inline) तथा डिस्प्ले सूत्र (display formulas) कैसे टाइप कर सकते हैं, amsmath पैकेज द्वारा प्रदान किए गए विस्तार क्या हैं, और गणित में फॉन्ट कैसे बदले जा सकते हैं।</span>


जटिल गणितीय अभिव्यक्तियों को सुंदर रूप में टाइप करना LaTeX की सबसे बड़ी विशेषताओं में से एक है। आप गणित को एक तार्किक ढंग से उस मोड में लिख सकते हैं जिसे 'math mode' कहा जाता है।

## Math mode

Math mode में रिक्त स्थान (spaces) को अनदेखा किया जाता है और अक्षरों के बीच सही रिक्ति (spacing) अपने आप लागू होती है (लगभग हमेशा ही)।

Math mode के दो प्रकार होते हैं:

* इनलाइन  (inline)
* डिस्प्ले (display)


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\begin{document}
A sentence with inline mathematics: $y = mx + c$.
A second sentence with inline mathematics: $5^{2}=3^{2}+4^{2}$.


A second paragraph containing display math.
\[
  y = mx + c
\]
See how the paragraph continues after the display.
\end{document}
```

आपको अन्य वेब स्थानों पर भी 'LaTeX-जैसा' गणितीय इनपुट देखने को मिल सकता है, उदाहरण के लिए वेब पेजों पर समीकरण दिखाने के लिए उपयोग किया जाने वाला MathJax सिस्टम। ये सिस्टम अक्सर LaTeX की वाक्य रचना (syntax) में थोड़े बहुत बदलावों के साथ दिखाई देते हैं पर वास्तव में ये ध्यान रखें कि ये LaTeX का उपयोग नहीं करते हैं।

<p
  class="hint">हमारे सभी उदाहरण <i>सही LaTeX</i> पर आधारित हैं। अगर आप किसी और संदर्भ में कुछ और अलग देखते हैं, तो इसका कारण यह हो सकता है कि वह उदाहरण वास्तव में LaTeX का उपयोग नहीं कर रहा होगा।</p>



### इनलाइन मैथ मोड और गणितीय संकेत

जैसा कि आप ऊपर देख सकते हैं, इनलाइन मैथ मोड को डॉलर चिन्ह की एक जोड़ी (`$...$`) से दर्शाया जाता है। यह काम इस संकेत `\( ... \)` का उपयोग करके भी किया जा सकता है।  

सरल अभिव्यक्तियों को बिना किसी विशेष मार्कअप के लिखा जा सकता है, और आप देखेंगे कि गणित सुंदर रूप से spaced होता है और अक्षर तिरछे (italic) होते हैं।

इनलाइन मैथ मोड अभिव्यक्ति की ऊर्ध्वाधर ऊँचाई को सीमित करता है ताकि सूत्र पैराग्राफ की लाइनस्पेसिंग को यथासंभव प्रभावित न करे।

ध्यान दें कि _सारी_ गणितीय सामग्री को मैथ के रूप में मार्कअप करना चाहिए, भले वह केवल एक अक्षर या अंक ही क्यों न हो। उदाहरण के लिए, आप LaTeX डॉक्यूमेंट में  `... $2$ ...` का उपयोग करें, न कि `... 2 ...` का। अन्यथा, यदि आपको गणित मोड में माइनस चिन्ह चाहिए, तो `... $-2$ ...` का प्रयोग करें और आप पायेंगे कि मैथ मोड में प्रयोग होने वाले अंकों का फॉन्ट, टेक्स्ट आदि आम तौर से प्रयुक्त होने वाले अंकों से कितना अलग हो सकता है (हालांकि यह डॉक्यूमेंट के वर्ग पर भी निर्भर करता है)।

इसके विपरीत, सावधान रहें कि कहीं गणित मोड की संरचना सामान्य टेक्स्ट में न आ जाए — जैसे कि कभी कभी आप सामान्य टेक्स्ट में भी डॉलर `$` का प्रयोग कर सकते हैं, या फ़ाइल के नामों में `_` का प्रयोग कर सकते हैं (ऐसी स्थिति में इन्हें `\$` और `\_` के रूप में ही लिखा जाना चाहिए)।

हम अपने डॉक्यूमेंट में आसानी से superscripts और subscripts भी जोड़ सकते हैं; इनके लिए क्रमशः `^` और `_` का प्रयोग किया जाता है।


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\begin{document}
Superscripts $a^{b}$ and subscripts $a_{b}$.
\end{document}
```

(आप कुछ उदाहरणों में देख सकते हैं कि superscript और subscript को बिना ब्रेसेस के भी लिखा जा सकता है, लेकिन यह आधिकारिक सिंटैक्स नहीं है और इससे गलती हो सकती है; आप मानक के रुप में हमेशा ब्रेसेस का उपयोग करें।)

Math mode में बहुत सारे विशेष कमांड होते हैं। इनमें से कुछ काफी सरल होते हैं, जैसे कि साइन `\sin` और और लॉगरिदम के लिए `\log`, या  ग्रीक अक्षर के लिए`\theta`।


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\begin{document}
Some mathematics: $y = 2 \sin \theta^{2}$.
\end{document}
```

हम यहाँ सभी मानक LaTeX math mode कमांड को कवर नहीं कर सकते, लेकिन आप के लिए ऑनलाइन ऐसे कई संसाधन उपलब्ध हैं जो इनका पूरा सेट बताते हैं। आप math mode के चिन्हों के लिए या कमांड खोजने के लिए [Detexify](https://detexify.kirelabs.org/classify.html) टूल का उपयोग कर सकते हैं।



### डिस्प्ले गणित (Display Mathematics)

डिस्प्ले मैथ मोड के लिए आप वही कमांड उपयोग कर सकते हैं जो इनलाइन के लिए करते हैं।

डिस्प्ले मैथ मोड को डिफ़ॉल्ट रूप से केंद्रित (centered) रूप में सेट किया जाता है और यह बड़ी समीकरणों के लिए उपयोग होता है जो किसी अनुच्छेद का हिस्सा होती हैं। ध्यान दें कि डिस्प्ले मैथ वातावरण में अनुच्छेद समाप्त नहीं हो सकता, इसलिए इसके स्रोत (source) में रिक्त पंक्तियाँ (blank lines) नहीं होनी चाहिए।

अनुच्छेद की शुरुआत हमेशा डिस्प्ले से *पहले* होनी चाहिए, इसलिए डिस्प्ले मैथ वातावरण से पहले एक खाली पंक्ति भी न छोड़ें। अगर आपको गणित की कई पंक्तियाँ लिखनी हैं, तो लगातार डिस्प्ले मैथ वातावरण का उपयोग न करें (इससे spacing असंगत हो सकती है); इसके बजाय `amsmath` पैकेज से आने वाले `align` जैसे मल्टी-लाइन डिस्प्ले वातावरण का उपयोग करें (जिसे आगे वर्णित किया गया है)।

यह विशेष रूप से इंटीग्रेशन जैसी गणनाओं के लिए उपयोगी होता है, उदाहरण के लिए:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\begin{document}
A paragraph about a larger equation
\[
\int_{-\infty}^{+\infty} e^{-x^2} \, dx
\]
\end{document}
```

ध्यान दें कि यहाँ subscript और superscript संकेतों का उपयोग इंटीग्रेशन की सीमाएँ सेट करने के लिए किया गया है।

हमने यहाँ एक मैन्युअल स्पेसिंग जोड़ी है: `\,` यह एक पतली रिक्ति (thin space) बनाता है जो `dx` से पहले जोड़ा गया है।


डिफरेंशियल ऑपरेटर `d` के फ़ॉर्मेटिंग में भिन्नता हो सकती है: कुछ प्रकाशक सीधे (upright) 'd' का उपयोग करते हैं, जबकि अन्य तिरछे (italic) *d* का। एक तरीका यह है कि आप अपने स्रोत में एक `\diff` कमांड बना लें जिसे ज़रूरत के अनुसार समायोजित किया जा सके, [उदाहरण के लिए](http://www.tug.org/TUGboat/tb41-1/tb127gregorio-math.pdf) यह देखें:


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\newcommand{\diff}{\mathop{}\!d}            % For italic
% \newcommand{\diff}{\mathop{}\!\mathrm{d}} % For upright
\begin{document}
A paragraph about a larger equation
\[
\int_{-\infty}^{+\infty} e^{-x^2} \diff x
\]
\end{document}
```

आप आमतौर पर जब एक क्रमांकित समीकरण बनाना चाहते हैं, तब इसे `equation` वातावरण का उपयोग करके बनाया जाता है।  
आइए वही उदाहरण फिर से आज़माते हैं:


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\begin{document}
A paragraph about a larger equation
\begin{equation}
\int_{-\infty}^{+\infty} e^{-x^2} \, dx
\end{equation}
\end{document}
```

समीकरण नंबर अपने आप बढ़ता है, जैसे कि इस उदाहरण में, या फिर अनुभाग संख्या के साथ भी यह बढ़ सकता है, जैसे अनुभाग 2 का पाँचवाँ समीकरण हो तो (2.5) इसका नंबर स्वतः ही बन जाता है।

फ़ॉर्मेटिंग का यह विवरण डॉक्यूमेंट के वर्ग (document class) द्वारा निर्धारित किया जाता है और यहाँ इसका वर्णन नहीं किया गया है।


## `amsmath` पैकेज

गणितीय संकेतों की भाषा बहुत समृद्ध है, और इसका मतलब है कि LaTeX के मूल (kernel) में जो टूल दिए गए हैं, वे सब कुछ कवर नहीं कर सकते। `amsmath` पैकेज मुख्य सपोर्ट को विस्तार देता है ताकि और भी कई गणितीय विचारों को शामिल किया जा सके। [`amsmath` उपयोगकर्ता गाइड](http://texdoc.org/pkg/amsmath) में इस पाठ में दिखाए गए उदाहरणों से कहीं और अधिक उदाहरण सीखने के लिए दिए गए हैं।


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{amsmath}

\begin{document}
Solve the following recurrence for $ n,k\geq 0 $:
\begin{align*}
  Q_{n,0} &= 1   \quad Q_{0,k} = [k=0];  \\
  Q_{n,k} &= Q_{n-1,k}+Q_{n-1,k-1}+\binom{n}{k}, \quad\text{for $n$, $k>0$.}
\end{align*}
\end{document}
```

`align*` वातावरण समीकरणों को ampersand, यानी `&` चिन्हों पर पंक्तिबद्ध करता है, ठीक वैसे ही जैसे किसी तालिका (table) में होता है। धयान दें कि हमने थोड़ी जगह जोड़ने के लिए `\quad` का उपयोग किया है, और गणित मोड के अंदर सामान्य टेक्स्ट डालने के लिए `\text` का प्रयोग किया है। साथ में, हमने एक और गणितीय कमांड, `\binom`, का उपयोग बायनॉमियल के लिए किया है।

यहाँ हमने `align*` का उपयोग किया है, इसलिए समीकरण क्रमांकित होकर नहीं आया। अधिकतर गणितीय वातावरणों में डिफ़ॉल्ट रूप से समीकरण क्रमांकित होते हैं, और जिन वेरिएंट्स में `*` लगा होता है, वे नंबरिंग को बंद कर देते हैं।

इस पैकेज में और भी कई सुविधाजनक वातावरण होते हैं, जैसे कि मैट्रिक्स (matrices) बनाने के लिए पैकेज।

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{amsmath}
\begin{document}
AMS matrices.
\[
\begin{matrix}
a & b & c \\
d & e & f
\end{matrix}
\quad
\begin{pmatrix}
a & b & c \\
d & e & f
\end{pmatrix}
\quad
\begin{bmatrix}
a & b & c \\
d & e & f
\end{bmatrix}
\]
\end{document}
```


## गणित मोड में फ़ॉन्ट्स

सामान्य टेक्स्ट के विपरीत, गणित मोड में फ़ॉन्ट बदलना अक्सर एक विशेष अर्थ को व्यक्त करता है। इसलिए इन्हें स्पष्ट रूप से लिखा जाता है। इसके लिए आपको कुछ कमांड्स की आवश्यकता होती है:

- `\mathrm`: रोमन (सीधा लेखन)
- `\mathit`: तिरछा लेखन, टेक्स्ट की तरह स्पेसिंग के साथ  
- `\mathbf`: मोटा अक्षर (boldface)
- `\mathsf`: सैन्स सेरिफ़
- `\mathtt`: मोनोस्पेस्ड (typewriter स्टाइल)
- `\mathbb`: डबल-स्ट्रक (blackboard bold) (`amsfonts` पैकेज द्वारा प्रदान किया गया)

इनमें से हर एक कमांड लैटिन अक्षरों को आर्ग्युमेंट के रूप में लेता है, उदाहरण के लिए हम एक मैट्रिक्स को इस प्रकार लिख सकते हैं:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\begin{document}
The matrix $\mathbf{M}$.
\end{document}
```

ध्यान दें कि डिफ़ॉल्ट मैथ इटालिक अक्षरों को अलग-अलग दिखाता है ताकि उन्हें विभिन्न चर (variables) के गुणनफल (product) के रूप में दर्शाया जा सके। अगर आपको कोई शब्द तिरछा (italic) दिखाना है, तो `\mathit` का उपयोग करें।

`\math..` फ़ॉन्ट कमांड्स गणित के लिए निर्दिष्ट फ़ॉन्ट्स का उपयोग करते हैं। कभी-कभी आपको कोई ऐसा शब्द लिखना होता है जो बाहरी वाक्य संरचना का हिस्सा होता है और उसे वर्तमान टेक्स्ट फ़ॉन्ट में दिखाना होता है, तो इसके लिए आप `\text{...}` का उपयोग कर सकते हैं (जो `amsmath` पैकेज द्वारा प्रदान किया गया है) या फिर विशेष फ़ॉन्ट स्टाइल जैसे `\textrm{..}` का प्रयोग कर सकते हैं।


```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{amsmath}
\begin{document}

$\text{bad use } size  \neq \mathit{size} \neq \mathrm{size} $

\textit{$\text{bad use } size \neq \mathit{size} \neq \mathrm{size} $}

\end{document}
```

अगर आपको अन्य चिह्नों को बोल्ड करना है, तो [अधिक जानकारी यहाँ देखें](more-10)।



## अभ्यास

चलिए, कुछ बुनियादी math mode का प्रयोग करके देखें: दिए गए उदाहरणों को इनलाइन और डिस्प्ले मोड के बीच बदलें।  
देखें कि इससे क्या प्रभाव पड़ता है।

अन्य ग्रीक अक्षर जोड़ने का प्रयास करें, छोटे (lowercase) और बड़े (uppercase) दोनों। आपको उनके नाम अनुमान से समझ में आ जाने चाहिए।

फ़ॉन्ट बदलने वाले कमांड्स के साथ प्रयोग करें: देखें कि जब आप उन्हें एक-दूसरे के भीतर (nest) करते हैं तो क्या होता है।

डिस्प्ले मोड में गणित डिफ़ॉल्ट रूप से केंद्रित (centered) होता है; ऊपर दिए गए कुछ उदाहरणों में 'डॉक्यूमेंट वर्ग विकल्प `[fleqn]` (flush left equation)' को जोड़कर देखें कि लेआउट कैसे बदलता है। इसी तरह, समीकरण संख्या आमतौर पर दाईं ओर हो जाती है। एक अन्य दस्तावेज़ वर्ग विकल्प `[leqno]` (left equation numbers) को भी जोड़कर देखें कि क्या होता है।

