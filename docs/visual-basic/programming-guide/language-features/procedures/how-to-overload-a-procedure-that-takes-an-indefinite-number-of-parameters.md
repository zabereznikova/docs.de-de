---
title: "How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic) | Microsoft Docs"
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
  - "procedure overloading, indefinite number of parameters"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedure parameters"
  - "procedures, overloading"
  - "procedures, multiple versions"
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn eine Prozedur über einen [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)\-Parameter verfügt, können Sie keine überladene Version definieren, die ein eindimensionales Array für das Parameterarray akzeptiert.  Weitere Informationen finden Sie im Abschnitt "Implizite Überladungen für ParamArray\-Parameter" unter [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
### So überladen Sie eine Prozedur, die eine variable Anzahl von Parametern akzeptiert  
  
1.  Stellen Sie fest, ob die Prozedur\- und Aufrufcodelogik von überladenen Versionen mehr profitiert als von einem `ParamArray`\-Parameter.  Siehe "Überladungen und ParamArrays" unter [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
2.  Bestimmen Sie, welche Anzahl von angegebenen Werten die Prozedur im variablen Teil der Parameterliste akzeptieren sollte.  Hierbei sind der Fall keiner Wertangabe und der Fall eines einzelnen eindimensionalen Arrays zu berücksichtigen.  
  
3.  Schreiben Sie für jede akzeptable Anzahl angegebener Werte eine `Sub`\-Deklarationsanweisung oder `Function`\-Deklarationsanweisung, die die entsprechende Parameterliste definiert.  Verwenden Sie weder das `Optional`\-Schlüsselwort noch das `ParamArray`\-Schlüsselwort in dieser überladenen Version.  
  
4.  Stellen Sie in jeder Deklaration das [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)\-Schlüsselwort dem `Sub`\-Schlüsselwort bzw. dem `Function`\-Schlüsselwort voran.  
  
5.  Geben Sie nach jeder Deklaration den Prozedurcode ein, der ausgeführt werden soll, wenn im Aufrufcode Werte angegeben werden, die der Parameterliste der betreffenden Deklaration entsprechen.  
  
6.  Beenden Sie jede Prozedur nach Bedarf mit der `End Sub`\-Anweisung oder der `End Function`\-Anweisung.  
  
## Beispiel  
 Im folgenden Beispiel wird eine mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)\-Parameter definierte Prozedur gezeigt und danach ein entsprechender Satz überladener Prozeduren.  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 Sie können eine solche Prozedur nicht mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.  Sie können jedoch die Signaturen der anderen impliziten Überladungen verwenden.  Die folgenden Deklarationen verdeutlichen dies.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 Im Code der überladenen Versionen muss nicht überprüft werden, ob der Aufrufcode einen oder mehrere Werte für den `ParamArray`\-Parameter angegeben hat, und wenn dies der Fall war, wie viele Werte bereitgestellt wurden.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] übergibt die Steuerung der Version, zu der die angegebene Argumentliste passt.  
  
## Kompilieren des Codes  
 Weil eine Prozedur mit einem `ParamArray`\-Parameter einer Gruppe von überladenen Versionen entspricht, kann eine solche Prozedur nicht mit einer Parameterliste überladen werden, die einer dieser impliziten Überladungen entspricht.  Weitere Informationen hierzu finden Sie unter [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## .NET Framework-Sicherheit  
 Wenn Sie mit einem Array arbeiten, das unendlich groß sein kann, besteht die Gefahr, dass eine interne Kapazität der Anwendung überschritten wird.  Wenn Sie ein Parameterarray akzeptieren, müssen Sie die Länge des Arrays überprüfen, das vom Aufrufcode übergeben wird, und die entsprechenden Maßnahmen ergreifen, wenn es für die Anwendung zu groß ist.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)