---
title: 'Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- inheritance, COM reusability
- base classes, COM reusability
- inheritance, walkthroughs
- derived classes, COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fa7753847619f14600c924cba01e55651c4f17c2
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic)
Sie können von Visual Basic-Klassen ableiten `Public` Klassen in COM-Objekte, auch solche, die in früheren Versionen erstellten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Die Eigenschaften und Methoden von Klassen geerbt von COM-Objekte können überschrieben oder überladen, wie Eigenschaften und Methoden jeder anderen Basisklasse überschrieben oder überladen werden können. Vererbung von COM-Objekten ist nützlich, wenn Sie eine vorhandene Klassenbibliothek verfügen, die nicht neu kompiliert werden sollen.  
  
 Das folgende Verfahren veranschaulicht, wie Visual Basic 6.0 verwenden, um ein COM-Objekt zu erstellen, die eine Klasse enthält, und dann als Basisklasse verwenden.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Das COM-Objekt zu erstellen, das in dieser exemplarischen Vorgehensweise verwendet wird  
  
1.  Öffnen Sie in Visual Basic 6.0 ein neues ActiveX DLL-Projekt. Ein Projekt namens `Project1` wird erstellt. Eine Klasse mit dem Namen `Class1`.  
  
2.  In der **Projekt-Explorer**, mit der rechten Maustaste **Project1**, und klicken Sie dann auf **Eigenschaften von Project1**. Die **Projekteigenschaften** Dialogfeld wird angezeigt.  
  
3.  Auf der **allgemeine** auf der Registerkarte der **Projekteigenschaften** Dialogfeld ändern den Namen des Projekts durch Eingabe `ComObject1` in der **Projektname** Feld.  
  
4.  In der **Projekt-Explorer**, mit der rechten Maustaste `Class1`, und klicken Sie dann auf **Eigenschaften**. Die **Eigenschaften** für die Klasse wird angezeigt.  
  
5.  Ändern der `Name` -Eigenschaft `MathFunctions`.  
  
6.  In der **Projekt-Explorer**, mit der rechten Maustaste `MathFunctions`, und klicken Sie dann auf **Anzeigecode**. Die **Code-Editor** wird angezeigt.  
  
7.  Fügen Sie eine lokale Variable den Wert der Eigenschaft hinzu:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Fügen Sie die Eigenschaft `Let` und `Get` Eigenschaftenprozeduren:  
  
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
  
10. Erstellen und registrieren Sie das COM-Objekt, indem Sie auf **stellen ComObject1.dll** auf der **Datei** Menü.  
  
    > [!NOTE]
    >  Obwohl Sie auch eine mit erstellte Klasse verfügbar gemacht werden können [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] als COM-Objekt ist ein echtes COM-Objekt und kann nicht in dieser exemplarischen Vorgehensweise verwendet werden. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Interop-Assemblys  
 In der folgenden Prozedur erstellen Sie eine Interop-Assembly, die fungiert als Brücke zwischen nicht verwaltetem Code (z. B. ein COM-Objekt) und verwaltetem Code [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] verwendet. Die Interop-Assembly, die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] viele Details der Arbeit mit COM-Objekten, z. B. Handles erstellt *Interop-Marshalling*, der Prozess Zusammenfassen von Parametern und Rückgabewerten in äquivalente Typen, wie sie die an und von COM-Objekten wechseln. Der Verweis in der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verweist auf die Interop-Assembly, nicht auf das eigentliche COM-Objekt.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Ein COM-Objekt mit Visual Basic 2005 und höheren Versionen verwenden  
  
1.  Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows-Anwendungsprojekt.  
  
2.  Auf der **Projekt** Menü klicken Sie auf **Verweis hinzufügen**.  
  
     Die **Verweis hinzufügen** Dialogfeld wird angezeigt.  
  
3.  Auf der **COM** Registerkarte, doppelklicken Sie auf `ComObject1` in der **Komponentenname** aus, und klicken Sie auf **OK**.  
  
4.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
     Die **neues Element hinzufügen** Dialogfeld wird angezeigt.  
  
5.  In der **Vorlagen** Bereich, klicken Sie auf **Klasse**.  
  
     Der Standarddateiname `Class1.vb`, wird in der **Namen** Feld. Ändern Sie dieses Feld in MathClass.vb, und klicken Sie auf **hinzufügen**. Dadurch wird eine Klasse namens `MathClass`, und ihr Code angezeigt.  
  
6.  Fügen Sie den folgenden Code am Anfang der `MathClass` von COM-Klasse erben.  
  
     [!code-vb[VbVbalrInterop&#31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Überladen Sie die öffentliche Methode der Basisklasse durch den folgenden Code hinzufügen `MathClass`:  
  
     [!code-vb[VbVbalrInterop&#32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Die geerbte Klasse erweitern, indem Sie den folgenden Code hinzufügen `MathClass`:  
  
     [!code-vb[VbVbalrInterop&33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 Die neue Klasse erbt die Eigenschaften der Basisklasse im COM-Objekt, überlädt eine Methode und definiert eine neue Methode, um die Klasse zu erweitern.  
  
#### <a name="to-test-the-inherited-class"></a>So testen Sie die geerbte Klasse  
  
1.  Dem Startformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um ihren Code anzuzeigen.  
  
2.  Die Schaltfläche `Click` Handler Ereignisprozedur, fügen Sie folgenden Code zum Erstellen einer Instanz von `MathClass` und die überladenen Methoden aufzurufen:  
  
     [!code-vb[VbVbalrInterop&#34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Führen Sie das Projekt, indem Sie F5 drücken.  
  
 Beim Anklicken der Schaltfläche auf dem Formular die `AddNumbers` -Methode zuerst aufgerufen wird und `Short` Datentyp Zahlen und [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wählt die entsprechende Methode der Basisklasse. Der zweite Aufruf von `AddNumbers` wird angewiesen, die überladene Methode von `MathClass`. Die dritte aufrufen, ruft die `SubtractNumbers` -Methode, die die Klasse erweitert. Die Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie haben möglicherweise bemerkt, die überladenen `AddNumbers` -Funktion hat den gleichen Datentyp wie die von der Basisklasse des COM-Objekts geerbte Methode. Dies wird als 16-Bit-Ganzzahlen vom Typ verfügbar gemacht werden, da die Argumente und Parameter der Methode der Basisklasse werden als 16-Bit-Ganzzahlen in Visual Basic 6.0 definiert `Short` in höheren Versionen von Visual Basic. Die neue Funktion akzeptiert 32-Bit-Ganzzahlen und Funktion der Basisklasse überlädt.  
  
 Bei der Arbeit mit COM-Objekte stellen Sie sicher, dass Sie die Größe und die Datentypen der Parameter überprüfen. Wenn Sie ein COM-Objekt, das ein Visual Basic 6.0-Auflistungsobjekt als Argument akzeptiert verwenden, können nicht Sie z. B. eine Sammlung aus einer höheren Version von Visual Basic bereitstellen.  
  
 Eigenschaften und Methoden, die von COM-Klassen geerbt können überschrieben werden dies bedeutet, dass Sie eine lokale Eigenschaft oder Methode, die eine Eigenschaft ersetzt oder von einer COM-Basisklasse geerbten Methode deklarieren können. Die Regeln für das Überschreiben von geerbter COM‑Eigenschaften ähneln denen für das Überschreiben anderer Eigenschaften und Methoden mit den folgenden Ausnahmen:  
  
-   Wenn Sie eine Eigenschaft oder Methode geerbt von einer COM-Klasse überschreiben, müssen Sie alle anderen geerbten Eigenschaften und Methoden überschreiben.  
  
-   Eigenschaften, mit denen `ByRef` Parameter können nicht überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Interoperabilität in .NET Framework-Clientanwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
