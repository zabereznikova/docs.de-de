---
title: "How to: Overload a Procedure that Takes Optional Parameters (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, parameters"
  - "procedure overloading, optional parameters"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedure parameters"
  - "procedures, overloading"
  - "procedures, multiple versions"
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wenn eine Prozedur einen oder mehrere [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)\-Parameter enthält, können Sie eine überladene Version definieren, die jeder der impliziten Überladungen entspricht.  Weitere Informationen finden Sie im Abschnitt "Implizite Überladungen für optionale Parameter" unter [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Ein optionaler Parameter  
  
#### So überladen Sie eine Prozedur, die einen optionalen Parameter akzeptiert  
  
1.  Schreiben Sie eine `Sub`\-Deklarationsanweisung oder eine `Function`\-Deklarationsanweisung, die den optionalen Parameter in der Parameterliste enthält.  Verwenden Sie das `Optional`\-Schlüsselwort nicht in dieser überladenen Version.  
  
2.  Stellen Sie dem `Sub`\-Schlüsselwort oder dem `Function`\-Schlüsselwort das [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)\-Schlüsselwort voran.  
  
3.  Schreiben Sie den Prozedurcode, der ausgeführt werden soll, wenn das optionale Argument im Aufrufcode nicht angegeben wird.  
  
4.  Beenden Sie die Prozedur nach Bedarf mit der `End Sub`\-Anweisung oder der `End Function`\-Anweisung.  
  
5.  Schreiben Sie eine zweite Deklarationsanweisung, die sich von der ersten Deklaration nur dadurch unterscheidet, dass der optionale Parameter nicht in der Parameterliste angegeben wird.  
  
6.  Schreiben Sie den Prozedurcode, der ausgeführt werden soll, wenn das optionale Argument im Aufrufcode nicht angegeben wird.  Beenden Sie die Prozedur nach Bedarf mit der `End Sub`\-Anweisung oder der `End Function`\-Anweisung.  
  
     Das folgende Beispiel veranschaulicht eine Prozedur, die mit einem optionalen Parameter definiert ist, eine äquivalente Gruppe mit zwei überladenen Prozeduren sowie Beispiele für ungültige und gültige überladene Versionen.  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## Mehrere optionale Parameter  
 Für eine Prozedur mit mehreren optionalen Parametern benötigen Sie normalerweise mehr als zwei überladene Versionen.  Wenn eine Prozedur beispielsweise zwei optionale Parameter enthält und im Aufrufcode jeder dieser Parameter unabhängig voneinander angegeben oder nicht angegeben werden kann, dann sind vier überladene Versionen erforderlich, nämlich eine Version für jede mögliche Kombination angegebener Argumente.  
  
 Mit zunehmender Anzahl von optionalen Parametern wird auch das Überladen komplexer.  Sofern es keine nicht akzeptablen Kombinationen angegebener Argumente gibt, sind für N optionale Parameter 2 ^ N überladene Versionen erforderlich.  Je nach Art der Prozedur, kann der zusätzliche Aufwand, den die Definition sämtlicher überladener Versionen bedeutet, durch die Verständlichkeit der Logik gerechtfertigt werden.  
  
#### So überladen Sie eine Prozedur, die mehrere optionale Parameter akzeptiert  
  
1.  Legen Sie fest, welche Kombinationen angegebener optionaler Argumente in Anbetracht der Logik der Prozedur akzeptabel sind.  Eine unannehmbare Kombination könnte entstehen, wenn ein optionaler Parameter von einem anderen abhängt.  Wenn ein Parameter beispielsweise den Namen des Ehegatten und ein anderer das Alter des Ehegatten enthalten soll, dann ist eine Kombination von Argumenten ungültig, die das Alter, aber nicht den Namen angibt.  
  
2.  Schreiben Sie für jede akzeptable Kombination angegebener Werte eine `Sub`\-Deklarationsanweisung bzw. eine `Function`\-Deklarationsanweisung, die die entsprechende Parameterliste definiert.  Verwenden Sie das `Optional`\-Schlüsselwort nicht.  
  
3.  Stellen Sie in jeder Deklaration das [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)\-Schlüsselwort dem `Sub`\-Schlüsselwort bzw. dem `Function`\-Schlüsselwort voran.  
  
4.  Geben Sie nach jeder Deklaration den Prozedurcode ein, der ausgeführt werden soll, wenn im Aufrufcode eine Argumentliste angegeben wird, die der Parameterliste der betreffenden Deklaration entspricht.  
  
5.  Beenden Sie jede Prozedur nach Bedarf mit der `End Sub`\-Anweisung oder der `End Function`\-Anweisung.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)