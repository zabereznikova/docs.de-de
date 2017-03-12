---
title: "Walkthrough: Implementing Inheritance with COM Objects (Visual Basic) | Microsoft Docs"
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
  - "inheritance, COM reusability"
  - "base classes, COM reusability"
  - "inheritance, walkthroughs"
  - "derived classes, COM reusability"
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Visual Basic\-Klassen können von `Public`\-Klassen aus COM\-Objekten abgeleitet werden, auch wenn diese mit früheren Versionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellt wurden.  Die von COM\-Objekten geerbten Eigenschaften und Methoden können auf die gleiche Weise überschrieben oder überladen werden wie Eigenschaften und Methoden jeder anderen Basisklasse.  Das Vererben von COM\-Objekten bietet sich an, wenn Sie eine vorhandene Klassenbibliothek nicht erneut kompilieren möchten.  
  
 In der folgenden Prozedur wird veranschaulicht, wie Sie mit Visual Basic 6.0 ein COM\-Objekt erstellen, das eine Klasse enthält, und wie Sie diese dann als Basisklasse verwenden.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So erstellen Sie das in dieser exemplarischen Vorgehensweise verwendete COM\-Objekt  
  
1.  Öffnen Sie in Visual Basic 6.0 ein neues ActiveX\-DLL\-Projekt.  Ein Projekt mit dem Namen `Project1` wird erstellt.  Es verfügt über eine Klasse mit dem Namen `Class1`.  
  
2.  Klicken Sie im **Projektexplorer** mit der rechten Maustaste auf **Project1**, und klicken Sie dann auf **Eigenschaften von Project1**.  Das Dialogfeld **Projekteigenschaften** wird angezeigt.  
  
3.  Ändern Sie im Dialogfeld **Projekteigenschaften** auf der Registerkarte **Allgemein** den Projektnamen, indem Sie im Feld **Projektname** den Namen `ComObject1` eingeben.  
  
4.  Klicken Sie im **Projektexplorer** mit der rechten Maustaste auf `Class1`, und klicken Sie dann auf **Eigenschaften**.  Das **Eigenschaftenfenster** wird für die Klasse angezeigt.  
  
5.  Ändern Sie die `Name`\-Eigenschaft in `MathFunctions`.  
  
6.  Klicken Sie im **Projektexplorer** mit der rechten Maustaste auf `MathFunctions`, und klicken Sie dann auf **Code anzeigen**.  Der **Code\-Editor** wird angezeigt.  
  
7.  Fügen Sie eine lokale Variable für den Eigenschaftswert hinzu:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Fügen Sie die Property `Let`\-Eigenschaftenprozedur und die Property `Get`\-Eigenschaftenprozedur hinzu:  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. Fügen Sie eine Funktion hinzu:  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. Erstellen und registrieren Sie das COM\-Objekt, indem Sie im Menü **Datei** auf **ComObject1.dll erstellen** klicken.  
  
    > [!NOTE]
    >  Sie können zwar auch eine mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellte Klasse als COM\-Objekt verfügbar machen, allerdings handelt es sich dann nicht um ein echtes COM\-Objekt. Ein solches Objekt kann in dieser exemplarischen Vorgehensweise nicht verwendet werden.  Ausführliche Informationen finden Sie unter [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## Interop\-Assemblys  
 In der folgenden Prozedur erstellen Sie eine Interop\-Assembly, die als Brücke zwischen nicht verwaltetem Code \(z. B. einem COM\-Objekt\) und dem verwalteten Code von [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] fungiert.  Die von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellte Interop\-Assembly deckt viele Details der Arbeit mit COM\-Objekten ab, wie beispielsweise *Interop\-Marshalling*, d. i. das Zusammenfassen von Parametern und Rückgabewerten in äquivalente Datentypen, wenn diese an COM\-Objekte und von COM\-Objekten übergeben werden.  Der Verweis in der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Anwendung zeigt auf die Interop\-Assembly, nicht auf das eigentliche COM\-Objekt.  
  
#### So verwenden Sie ein COM\-Objekt mit Visual Basic 2005 und höheren Versionen  
  
1.  Öffnen Sie ein neues [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Windows\-Anwendungsprojekt.  
  
2.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**.  
  
     Das Dialogfeld **Verweis hinzufügen** wird angezeigt.  
  
3.  Doppelklicken Sie auf der Registerkarte **COM** in der Liste **Komponentenname** auf `ComObject1`, und klicken Sie auf **OK**.  
  
4.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
5.  Klicken Sie im Bereich **Vorlagen** auf **Klasse**.  
  
     Der Standarddateiname, `Class1.vb`, wird im Feld **Name** angezeigt.  Ändern Sie den Eintrag in diesem Feld in MathClass.vb, und klicken Sie auf **Hinzufügen**.  Dadurch wird eine Klasse mit dem Namen `MathClass` erstellt und ihr Code angezeigt.  
  
6.  Fügen Sie folgenden Code am Anfang von `MathClass` ein, damit die Klasse von der COM\-Klasse erbt.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#31)]  
  
7.  Überladen Sie die public\-Methode der Basisklasse, indem Sie `MathClass` den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#32)]  
  
8.  Erweitern Sie die geerbte Klasse, indem Sie `MathClass` den folgenden Code hinzufügen:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#33)]  
  
 Die neue Klasse erbt die Eigenschaften der Basisklasse im COM\-Objekt, überlädt eine Methode und definiert eine neue Methode, um die Klasse zu erweitern.  
  
#### So testen Sie die geerbte Klasse  
  
1.  Fügen Sie dem Startformular eine Schaltfläche hinzu, und doppelklicken Sie anschließend darauf, um ihren Code anzuzeigen.  
  
2.  Fügen Sie der Ereignishandlerprozedur für das `Click`\-Ereignis der Schaltfläche folgenden Code hinzu, um eine Instanz von `MathClass` zu erstellen und die überladenen Methoden aufzurufen:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#34)]  
  
3.  Führen Sie das Projekt aus, indem Sie F5 drücken.  
  
 Wenn Sie auf die Schaltfläche im Formular klicken, wird zuerst die `AddNumbers`\-Methode mit Zahlen vom Datentyp `Short` aufgerufen. Die entsprechende Methode der Basisklasse wird von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ausgewählt.  Der zweite Aufruf von `AddNumbers` wird an die überladene Methode von `MathClass` weitergeleitet.  Der dritte Aufruf ruft die `SubtractNumbers`\-Methode auf, die die Klasse erweitert.  Die Eigenschaft der Basisklasse wird festgelegt, und der Wert wird angezeigt.  
  
## Nächste Schritte  
 Die überladene `AddNumbers`\-Funktion scheint zum gleichen Datentyp zu gehören wie die von der Basisklasse des COM\-Objekts geerbte Methode.  Dies liegt daran, dass die Argumente und Parameter der Methode der Basisklasse in Visual Basic 6.0 als 16\-Bit\-Ganzzahlen definiert sind, jedoch in höheren Visual Basic\-Versionen als 16\-Bit\-Ganzzahlen vom Typ `Short` verfügbar gemacht werden.  Die neue Funktion übernimmt 32\-Bit\-Ganzzahlen und überlädt die Funktion der Basisklasse.  
  
 Überprüfen Sie daher bei COM\-Objekten stets die Größe und den Datentyp von Parametern.  Wenn Sie z. B. ein COM\-Objekt verwenden, das ein Visual Basic 6.0\-Auflistungsobjekt als Argument akzeptiert, können Sie keine Auflistung aus höheren Visual Basic\-Versionen angeben.  
  
 Eigenschaften und Methoden, die von COM‑Klassen geerbt wurden, können überschrieben werden. Das heißt, Sie können eine lokale Eigenschaft oder Methode deklarieren, die eine aus einer Basis\-COM‑Klasse geerbte Eigenschaft oder Methode ersetzt.  Die Regeln für das Überschreiben von geerbten COM‑Eigenschaften ähneln denen für das Überschreiben anderer Eigenschaften und Methoden, wobei folgende Ausnahmen gelten:  
  
-   Wenn Sie eine einzelne Eigenschaft oder Methode überschreiben, die von einer COM‑Klasse geerbt wurde, müssen Sie auch alle anderen geerbten Eigenschaften und Methoden überschreiben.  
  
-   Eigenschaften, die `ByRef`\-Parameter verwenden, können nicht überschrieben werden.  
  
## Siehe auch  
 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)