---
title: "Namespace Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Namespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "namespaces, root"
  - "Namespace statement"
  - "namespaces, nested"
  - "declaring namespaces, syntax"
  - "namespaces, declaring"
  - "root namespaces"
  - "declarations, namespaces"
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
caps.latest.revision: 39
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 39
---
# Namespace Statement
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Deklariert den Namen eines Namespaces und bewirkt, dass der auf die Deklaration folgende Quellcode in diesem Namespace kompiliert wird.  
  
## Syntax  
  
```  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## Teile  
 Global  
 Optional.  Hiermit können Sie einen Namespace aus dem Stammnamespace des Projekts zu definieren.  Weitere Informationen finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Erforderlich.  Ein eindeutiger Name, der den Namespace bezeichnet.  Muss ein gültiger Visual Basic\-Bezeichner sein.  Weitere Informationen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Optional.  Elemente, aus denen sich der Namespace zusammensetzt.  Dazu zählen, aber nicht für Strukturen, Enumerationen, Schnittstellen, Klassen, Module, Delegaten und andere Namespaces beschränkt.  
  
 `End Namespace`  
 Beendet einen `Namespace`\-Block.  
  
## Hinweise  
 Namespaces fungieren als Organisationssystem.  Sie bieten eine Möglichkeit zum Klassifizieren und Darstellen von Programmierelementen, die für andere Programme und Anwendungen verfügbar gemacht werden.  Beachten Sie, dass ein Namespace kein *Typ* ist insofern, dass eine Klasse oder Struktur sein\-Sie kein Programmierelement deklarieren können, um den Datentyp eines Namespace verfügen.  
  
 Alle Programmierelemente, die nach einer `Namespace`\-Anweisung deklariert werden, gehören zu diesem Namespace.  Visual Basic kompiliert Elemente in den zuletzt deklarierten Namespace, bis entweder eine `End Namespace`\-Anweisung oder eine andere `Namespace`\-Anweisung auftritt.  
  
 Wenn ein Namespace bereits definiert ist, auch außerhalb des Projekts, können Sie diesem Programmierelemente hinzufügen.  Hierzu verwenden Sie eine `Namespace`\-Anweisung Visual Basic auf sie verweisen um Elemente in diesen Namespace zu kompilieren.  
  
 Sie können eine `Namespace`\-Anweisung nur auf Datei\- oder Namespaceebene verwenden.  Dies bedeutet, dass der *Deklarationskontext* für einen Namespace eine Quelldatei oder ein anderer Namespace sein muss und keine Klasse, keine Struktur, kein Modul, keine Schnittstelle und keine Prozedur sein kann.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Sie können einen Namespace in einem anderen Namespace deklarieren.  Die Anzahl der Schachtelungsebenen, die Sie deklarieren können, ist nicht streng begrenzt, allerdings sollten Sie Folgendes beachten: Wenn anderer Code auf die im innersten Namespace deklarierten Elemente zugreift, muss ein Qualifizierungspfad verwendet werden, der alle Namespacenamen der Schachtelungshierarchie enthält.  
  
## Zugriffsebene  
 Namespaces werden behandelt, als wäre sie eine `Public` Zugriffsebene aufweisen.  Auf einen Namespace kann von Code an einer beliebigen Stelle in demselben Projekt, von anderen Projekten, die auf dieses Projekt verweisen, und von einer aus dem Projekt erstellten Assembly aus zugegriffen werden.  
  
 Programmierelemente, die auf Namespaceebene deklariert sind, d. h. in einem Namespace, jedoch in keinem anderen Element, können `Public`\-Zugriff oder `Friend`\-Zugriff aufweisen.  Wenn keine Zugriffsebene angegeben wurde, ist die Standardzugriffsebene eines solchen Elements `Friend`.  Zu den Elementen, die Sie auf Namespaceebene deklarieren können, zählen Klassen, Strukturen, Module, Schnittstellen, Enumerationen und Delegaten.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## Stamm\-Namespace  
 Alle Namespacenamen im Projekt beruhen auf einem *Stammnamespace*.  Visual Studio weist den Projektnamen als Standardstammnamespace für den gesamten Code in diesem Projekt zu.  Wenn der Name des Projekts z. B. `Payroll` lautet, gehören die Programmierelemente des Projekts zu dem Namespace `Payroll`.  Wenn Sie `Namespace funding` deklarieren, ist der vollständige Name dieses Namespaces `Payroll.funding`.  
  
 Wenn Sie einen vorhandenen Namespace in einer `Namespace`\-Anweisung angeben möchten, wie z. B. im Beispiel für die generische Listenklasse, können Sie den Stammnamespace auf einen NULL\-Wert festlegen.  Klicken Sie hierfür im Menü **Projekt** auf **Projekteigenschaften**, und löschen Sie den Eintrag **Stammnamespace**.  Wenn Sie diesen Schritt im Beispiel für die generische Listenklasse nicht ausführen, verwendet der Visual Basic\-Compiler `System.Collections.Generic` als neuen Namespace im Projekt `Payroll`, mit dem vollständigen Namen `Payroll.System.Collections.Generic`.  
  
 Stattdessen können Sie auch mit dem `Global`\-Schlüsselwort auf Elemente von Namespaces verweisen, die außerhalb des Projekts definiert sind.  So kann der Projektname als Stammnamespace beibehalten werden.  Hierdurch wird die Wahrscheinlichkeit verringert, dass Ihre Programmierelemente versehentlich mit den Programmierelementen vorhandener Namespaces zusammengeführt werden.  Weitere Informationen finden Sie im Abschnitt „globales Schlüsselwort in den voll gekennzeichneten Namen“ \- Abschnitt in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 Das `Global`\-Schlüsselwort kann in einem Namespace Statement ebenfalls verwendet werden.  Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts Bereichs definieren.  Weitere Informationen finden Sie im Abschnitt „globales Schlüsselwort in den Namespace\-Anweisungen im Abschnitt“ [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **Problembehandlung** Der Stammnamespace kann zu unerwarteten Verkettungen von Namespacenamen führen.  Wenn Sie auf außerhalb des Projekts definierte Namespaces verweisen, können diese vom Visual Basic\-Compiler als geschachtelte Namespaces im Stammnamespace interpretiert werden.  In diesem Fall erkennt der Compiler keine Typen, die bereits in den externen Namespaces definiert wurden.  Um dies zu vermeiden, legen Sie den Stammnamespace auf einen NULL\-Wert fest, wie in „Stamm\-Namespace“ beschrieben und verwendet das Schlüsselwort `Global` von Elementen aus externen Namespaces zuzugreifen.  
  
## Attribute und Modifizierer  
 Sie können auf einen Namespace keine Attribute anwenden.  Ein Attribut fügt den Metadaten einer Assembly Informationen hinzu. Dies ist für Herkunftsklassifizierer wie Namespaces nicht sinnvoll.  
  
 Sie können auf einen Namespace weder Zugriffs\- noch Prozedurmodifizierer oder andere Modifizierer anwenden.  Da ein Namespace kein Typ ist, sind diese Modifizierer nicht sinnvoll.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei ineinander geschachtelte Namespaces deklariert.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel werden mehrere geschachtelte Namespaces in einer einzigen Zeile deklariert. Dieses Beispiel entspricht dem vorherigen Beispiel.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_2.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird auf die in den vorherigen Beispielen definierte Klasse zugegriffen.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_3.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird das Skelett einer neuen generischen Listenklasse definiert und dem <xref:System.Collections.Generic?displayProperty=fullName>\-Namespace hinzugefügt.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## Siehe auch  
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)