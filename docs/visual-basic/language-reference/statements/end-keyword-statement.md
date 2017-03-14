---
title: "End &lt;keyword&gt; Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.EndDefinition"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "End keyword"
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# End &lt;keyword&gt; Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wenn ein weiteres Schlüsselwort folgt, wird die Definition des durch dieses Schlüsselwort eingeleiteten Anweisungsblocks beendet.  
  
## Syntax  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## Teile  
 `End`  
 Erforderlich.  Beendet die Definition des Programmierelements.  
  
 `AddHandler`  
 Erforderlich, um einen `AddHandler`\-Accessor zu beenden, der in einer benutzerdefinierten [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) durch eine entsprechende `AddHandler`\-Anweisung eingeleitet wird.  
  
 `Class`  
 Erforderlich, um eine durch eine entsprechende [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) angefangene Klassendefinition zu beenden.  
  
 `Enum`  
 Erforderlich, um eine durch eine entsprechende [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) angefangene Enumerationsdefinition zu beenden.  
  
 `Event`  
 Erforderlich, um eine durch eine entsprechende [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) angefangene `Custom`\-Ereignisdefinition zu beenden.  
  
 `Function`  
 Erforderlich, um eine durch eine entsprechende [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) angefangene `Function`\-Prozedurdefinition zu beenden.  Wenn bei der Ausführung eine `End` `Function`\-Anweisung gefunden wird, wird die Steuerung an den Aufrufcode zurückgegeben.  
  
 `Get`  
 Erforderlich, um eine durch eine entsprechende [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) angefangene `Property`\-Prozedurdefinition zu beenden.  Wenn bei der Ausführung eine `End` `Get`\-Anweisung gefunden wird, wird die Steuerung an die Anweisung zurückgegeben, durch die der Wert der Eigenschaft angefordert wird.  
  
 `If`  
 Erforderlich, um eine `If`...`Then`...`Else`\-Blockdefinition zu beenden, die durch eine entsprechende `If`\-Anweisung eingeleitet wird.  Weitere Informationen finden Sie unter [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 Erforderlich, um eine durch eine entsprechende [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) angefangene Schnittstellendefinition zu beenden.  
  
 `Module`  
 Erforderlich, um eine durch eine entsprechende [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md) angefangene Moduldefinition zu beenden.  
  
 `Namespace`  
 Erforderlich, um eine durch eine entsprechende [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) angefangene Namespacedefinition zu beenden.  
  
 `Operator`  
 Erforderlich, um eine durch eine entsprechende [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md) angefangene Operatordefinition zu beenden.  
  
 `Property`  
 Erforderlich, um eine durch eine entsprechende [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) angefangene Eigenschaftendefinition zu beenden.  
  
 `RaiseEvent`  
 Erforderlich, um einen `RaiseEvent`\-Accessor zu beenden, der in einer benutzerdefinierten [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) durch eine entsprechende `RaiseEvent`\-Anweisung eingeleitet wird.  
  
 `RemoveHandler`  
 Erforderlich, um einen `RemoveHandler`\-Accessor zu beenden, der in einer benutzerdefinierten [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) durch eine entsprechende `RemoveHandler`\-Anweisung eingeleitet wird.  
  
 `Select`  
 Erforderlich, um eine `Select`...`Case`\-Blockdefinition zu beenden, die durch eine entsprechende `Select`\-Anweisung eingeleitet wird.  Weitere Informationen finden Sie unter [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Erforderlich, um eine durch eine entsprechende [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) angefangene `Property`\-Prozedurdefinition zu beenden.  Wenn bei der Ausführung eine `End` `Set`\-Anweisung gefunden wird, wird die Steuerung an die Anweisung zurückgegeben, durch die der Wert der Eigenschaft festgelegt wird.  
  
 `Structure`  
 Erforderlich, um eine durch eine entsprechende [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) angefangene Strukturdefinition zu beenden.  
  
 `Sub`  
 Erforderlich, um eine durch eine entsprechende [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) angefangene `Sub`\-Prozedurdefinition zu beenden.  Wenn bei der Ausführung eine `End` `Sub`\-Anweisung gefunden wird, wird die Steuerung an den Aufrufcode zurückgegeben.  
  
 `SyncLock`  
 Erforderlich, um eine `SyncLock`\-Blockdefinition zu beenden, die durch eine entsprechende `SyncLock`\-Anweisung eingeleitet wird.  Weitere Informationen finden Sie unter [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Erforderlich, um eine `Try`...`Catch`...`Finally`\-Blockdefinition zu beenden, die durch eine entsprechende `Try`\-Anweisung eingeleitet wird.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Erforderlich, um eine `While`\-Schleifendefinition zu beenden, die durch eine entsprechende `While`\-Anweisung eingeleitet wird.  Weitere Informationen finden Sie unter [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Erforderlich, um eine `With`\-Blockdefinition zu beenden, die durch eine entsprechende `With`\-Anweisung eingeleitet wird.  Weitere Informationen finden Sie unter [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## Hinweise  
 Bei Verwendung der [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)\-Anweisung ohne zusätzliches Schlüsselwort wird die Ausführung sofort beendet.  
  
 Wenn der Anweisung ein Nummernzeichen \(`#`\) vorangeht, wird mit dem `End`\-Schlüsselwort ein Präprozessorblock beendet, der durch die entsprechende Direktive eingeleitet wird.  
  
 `#End`  
 Erforderlich.  Beendet die Definition des Prärprozessorblocks.  
  
 `#ExternalSource`  
 Erforderlich, um einen externen Quellblock zu beenden, der durch eine entsprechende [\#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) eingeleitet wird.  
  
 `#If`  
 Erforderlich, um einen Block für die bedingte Kompilierung zu beenden, der durch eine entsprechende `#If`\-Direktive eingeleitet wird.  Weitere Informationen finden Sie unter [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 Erforderlich, um einen Quellbereichsblock zu beenden, der durch eine entsprechende [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) eingeleitet wird.  
  
## Hinweise für Entwickler intelligenter Geräte  
 Die `End`\-Anweisung ohne zusätzliches Schlüsselwort wird nicht unterstützt.  
  
## Siehe auch  
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)