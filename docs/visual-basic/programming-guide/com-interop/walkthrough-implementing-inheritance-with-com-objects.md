---
title: 'Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d6906c58431a0e844e8f430ade10ae819e77ff2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic)
Sie können aus Visual Basic-Klassen ableiten `Public` Klassen in COM-Objekte, einschließlich derer, die in früheren Versionen von erstellte [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Die Eigenschaften und Methoden von Klassen geerbt von COM-Objekte können außer Kraft gesetzt oder überladen, ebenso wie die Eigenschaften und Methoden der anderen Basisklasse überschreiben oder überladen werden können. Vererbung von COM-Objekten ist nützlich, wenn Sie eine vorhandene Klassenbibliothek verfügen, die nicht neu kompiliert werden soll.  
  
 Das folgende Verfahren veranschaulicht, wie Visual Basic 6.0 verwenden, um ein COM-Objekt zu erstellen, die eine Klasse enthält, und klicken Sie dann als Basisklasse verwenden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Das COM-Objekt zu erstellen, das in dieser exemplarischen Vorgehensweise verwendet wird  
  
1.  Öffnen Sie in Visual Basic 6.0 ein neues ActiveX-DLL-Projekt ein. Ein Projekt namens `Project1` wird erstellt. Es wurde eine Klasse namens `Class1`.  
  
2.  In der **Projektexplorer**, mit der rechten Maustaste **Projekt1**, und klicken Sie dann auf **Projekt1 Eigenschaften**. Die **Projekteigenschaften** Dialogfeld wird angezeigt.  
  
3.  Auf der **allgemeine** auf der Registerkarte die **Projekteigenschaften** Dialogfeld Feld, das den Namen des Projekts durch Eingabe ändern `ComObject1` in der **Projektname** Feld.  
  
4.  In der **Projektexplorer**, mit der rechten Maustaste `Class1`, und klicken Sie dann auf **Eigenschaften**. Die **Eigenschaften** Fenster für die Klasse wird angezeigt.  
  
5.  Ändern der `Name` Eigenschaft `MathFunctions`.  
  
6.  In der **Projektexplorer**, mit der rechten Maustaste `MathFunctions`, und klicken Sie dann auf **Code anzeigen**. Die **Code-Editor** wird angezeigt.  
  
7.  Fügen Sie eine lokale Variable, um den Wert der Eigenschaft hinzu:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Fügen Sie die Eigenschaft `Let` und Eigenschaft `Get` Eigenschaftenprozeduren:  
  
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
  
10. Erstellen und registrieren Sie das COM-Objekt, indem Sie auf **stellen ComObject1.dll** auf die **Datei** Menü.  
  
    > [!NOTE]
    >  Obwohl Sie auch eine Klasse, die mit erstellt verfügbar machen können [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] als COM-Objekt ist kein "true" COM-Objekt und kann nicht in dieser exemplarischen Vorgehensweise verwendet werden. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Interop-Assemblys  
 Im folgenden Verfahren erstellen Sie eine Interop-Assembly, die fungiert als Brücke zwischen nicht verwaltetem Code (z. B. ein COM-Objekt) und der verwaltete Code [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] verwendet. Die Interop-Assembly, die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erstellt Handles, die viele der Details der Arbeit mit COM-Objekte, z. B. *Interop-Marshalling*, der Prozess der Verpackung Parametern und Rückgabewerten in äquivalente Typen wie verschoben werden und COM-Objekten. Der Verweis in der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verweist auf die Interop-Assembly, nicht das eigentliche COM-Objekt.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Ein COM-Objekt mit Visual Basic 2005 und höheren Versionen verwenden  
  
1.  Öffnen Sie ein neues [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Windows-Anwendungsprojekt.  
  
2.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .  
  
     Die **Verweis hinzufügen** Dialogfeld wird angezeigt.  
  
3.  Auf der **COM** Registerkarte, doppelklicken Sie auf `ComObject1` in der **Komponentenname** aus, und klicken Sie auf **OK**.  
  
4.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
5.  In der **Vorlagen** Bereich, klicken Sie auf **Klasse**.  
  
     Der Standarddateiname `Class1.vb`, wird in der **Namen** Feld. Ändern Sie dieses Feld in MathClass.vb, und klicken Sie auf **hinzufügen**. Dies erstellt eine Klasse namens `MathClass`, und ihr Code angezeigt.  
  
6.  Fügen Sie den folgenden Code am Anfang `MathClass` von COM-Klasse erben.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Überladen, das die öffentliche Methode der Basisklasse durch den folgenden Code hinzufügen `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Die geerbte Klasse erweitern, indem Sie den folgenden Code hinzufügen `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 Die neue Klasse erbt die Eigenschaften der Basisklasse in der COM-Objekt, eine Methode überladen und definiert eine neue Methode zum Erweitern Sie die Klasse.  
  
#### <a name="to-test-the-inherited-class"></a>So testen Sie die geerbte Klasse  
  
1.  Das Startformular eine Schaltfläche hinzu, und doppelklicken Sie dann auf, um ihren Code anzuzeigen.  
  
2.  In der Schaltfläche `Click` Handler Ereignisprozedur, fügen Sie den folgenden Code zum Erstellen einer Instanz von `MathClass` und rufen Sie die überladenen Methoden:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Drücken Sie F5, um führen Sie das Projekt aus.  
  
 Wenn Sie das Formular auf die Schaltfläche, klicken Sie auf die `AddNumbers` -Methode zuerst aufgerufen wird, und `Short` Zahlen-Datentyp und [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] wählt die entsprechende Methode aus der Basisklasse. Der zweite Aufruf von `AddNumbers` gesteuert wird, um die Überladung der Methode aus `MathClass`. Rufen Sie das dritte Aufrufe der `SubtractNumbers` -Methode, die die Klasse erweitert. Die Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Ihnen möglicherweise aufgefallen, die die überladene `AddNumbers` Funktion kommt, haben den gleichen Datentyp wie die Methode, die von der Basisklasse des COM-Objekts vererbt. Dies ist die Argumente und Parameter der Methode der Basisklasse als 16-Bit-Ganzzahlen in Visual Basic 6.0 definiert sind, sondern als 16-Bit-Ganzzahlen vom Typ verfügbar gemacht werden `Short` in höheren Versionen von Visual Basic. Die neue Funktion akzeptiert 32-Bit-Ganzzahlen und Überladungen der Funktion der Basisklasse.  
  
 Bei der Arbeit mit COM-Objekte stellen Sie sicher, dass Sie die Größe und die Datentypen der Parameter überprüfen. Wenn Sie ein COM-Objekt, das ein Visual Basic 6.0-Auflistungsobjekt als Argument akzeptiert verwenden, können nicht Sie z. B. eine Sammlung aus einer neueren Version von Visual Basic bereitstellen.  
  
 Eigenschaften und Methoden, die von COM-Klassen geerbt können überschrieben werden dies bedeutet, dass eine lokale Eigenschaft oder Methode, die eine Eigenschaft ersetzt oder von einer COM-Basisklasse geerbte Methode deklariert werden können. Die Regeln für das Überschreiben von geerbter Eigenschaften von COM-ähneln den Regeln für das Überschreiben von anderen Eigenschaften und Methoden mit den folgenden Ausnahmen:  
  
-   Wenn Sie eine Eigenschaft oder Methode, die aus einer COM‑Klasse geerbt überschreiben, müssen Sie alle anderen geerbten Eigenschaften und Methoden überschreiben.  
  
-   Eigenschaften, mit denen `ByRef` Parameter können nicht überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
