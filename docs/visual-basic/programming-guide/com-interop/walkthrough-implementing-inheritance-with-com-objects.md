---
title: 'Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekte (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: e99deb2ea5e8acd5e1e07adffe29d35e2624b27e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648205"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekte (Visual Basic)
Sie können aus Visual Basic-Klassen ableiten `Public` Klassen in COM-Objekte, auch solche, die in früheren Versionen von Visual Basic erstellt. Die Eigenschaften und Methoden von Klassen geerbt von COM-Objekte können überschrieben oder überladen werden, wie Eigenschaften und Methoden von einer anderen Basisklasse überschrieben oder überladen werden können. Vererbung von COM-Objekten ist nützlich, wenn Sie eine vorhandene Klassenbibliothek verfügen, die nicht neu kompiliert werden sollen.  
  
 Das folgende Verfahren zeigt, wie Visual Basic 6.0 verwenden, um ein COM-Objekt zu erstellen, die eine Klasse enthält, und klicken Sie dann als Basisklasse verwendet wird.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Das COM-Objekt zu erstellen, das in dieser exemplarischen Vorgehensweise verwendet wird  
  
1.  Öffnen Sie in Visual Basic 6.0 ein neues ActiveX DLL-Projekt ein. Ein Projekt namens `Project1` erstellt wird. Es wurde eine Klasse namens `Class1`.  
  
2.  In der **Projektexplorer**, mit der rechten Maustaste **Projekt1**, und klicken Sie dann auf **Projekt1 Eigenschaften**. Die **Projekteigenschaften** Dialogfeld wird angezeigt.  
  
3.  Auf der **allgemeine** Registerkarte die **Projekteigenschaften** Dialogfeld ändern den Namen des Projekts durch Eingabe `ComObject1` in die **Projektname** Feld.  
  
4.  In der **Projektexplorer**, mit der rechten Maustaste `Class1`, und klicken Sie dann auf **Eigenschaften**. Die **Eigenschaften** Fenster für die Klasse wird angezeigt.  
  
5.  Ändern der `Name` Eigenschaft `MathFunctions`.  
  
6.  In der **Projektexplorer**, mit der rechten Maustaste `MathFunctions`, und klicken Sie dann auf **Ansichtscode**. Die **Code-Editor** wird angezeigt.  
  
7.  Fügen Sie eine lokale Variable für den Wert der Eigenschaft hinzu:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Fügen Sie Eigenschaft `Let` und `Get` Property-Prozeduren:  
  
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
    >  Obwohl Sie auch eine Klasse erstellt, die mit Visual Basic als COM-Objekt verfügbar machen können, ist nicht "true" COM-Objekt und kann nicht in dieser exemplarischen Vorgehensweise verwendet werden. Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Interop-Assemblys  
 Im folgenden Verfahren erstellen Sie eine interop-Assembly, fungiert als Brücke zwischen nicht verwalteten Code (z. B. ein COM-Objekt) und verwaltetem Code von den Visual Studio verwendet. Die Interop-Assembly, die Visual Basic erstellt behandelt viele der Details für die Arbeit mit COM-Objekten, z. B. *interop-Marshalling*, der Prozess der paketerstellung-Parameter und Rückgabewerte in äquivalente Typen wie verschoben werden und von COM-Objekten. Der Verweis in Visual Basic-Anwendung verweist auf die interop-Assembly, nicht die tatsächliche COM-Objekt.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Ein COM-Objekt mit Visual Basic 2005 und höheren Versionen verwenden.  
  
1.  Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.  
  
2.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .  
  
     Das Dialogfeld **Verweis hinzufügen** wird angezeigt.  
  
3.  Auf der **COM** Registerkarte, doppelklicken Sie auf `ComObject1` in die **Komponentenname** aus, und klicken Sie auf **OK**.  
  
4.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
5.  In der **Vorlagen** Bereich, klicken Sie auf **Klasse**.  
  
     Der Standarddateiname, `Class1.vb`, wird in der **Namen** Feld. Ändern Sie dieses Feld MathClass.vb, und klicken Sie auf **hinzufügen**. Dies erstellt eine Klasse namens `MathClass`, und ihr Code angezeigt.  
  
6.  Fügen Sie den folgenden Code am Anfang `MathClass` von COM-Klasse erben.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Überladen Sie die öffentliche Methode der Basisklasse durch den folgenden Code hinzufügen `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Die geerbte Klasse erweitern, indem Sie den folgenden Code hinzufügen `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 Die neue Klasse erbt die Eigenschaften der Basisklasse in das COM-Objekt, Überladungen eine Methode und eine neue Methode zum Erweitern Sie die Klasse definiert.  
  
#### <a name="to-test-the-inherited-class"></a>Um die geerbte Klasse zu testen.  
  
1.  Das Startformular fügen Sie eine Schaltfläche hinzu, und doppelklicken Sie darauf, um ihren Code anzuzeigen.  
  
2.  In der Schaltfläche `Click` Ereignishandlerprozedur, fügen Sie den folgenden Code zum Erstellen einer Instanz von `MathClass` die überladenen Methoden aufrufen:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Führen Sie das Projekt durch Drücken von F5.  
  
 Beim Anklicken der Schaltfläche im Formular die `AddNumbers` -Methode zuerst aufgerufen, wobei `Short` Daten geben Sie Zahlen ein, und Visual Basic wählt die entsprechende Methode aus der Basisklasse. Der zweite Aufruf von `AddNumbers` gesteuert wird, um die überladene Methode von `MathClass`. Die dritte Aufrufe der `SubtractNumbers` -Methode, die die Klasse erweitert. Die Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie haben vielleicht festgestellt, die den überladenen `AddNumbers` Funktion angezeigt wird, um den gleichen Datentyp wie die von der Basisklasse des COM-Objekts geerbte Methode zu erhalten. Dies ist, da die Argumente und Parameter der Methode der Basisklasse als 16-Bit-Ganzzahlen in Visual Basic 6.0 definiert sind, aber sie werden als 16-Bit-Ganzzahlen vom Typ verfügbar gemacht `Short` in höheren Versionen von Visual Basic. Die neue Funktion akzeptiert die 32-Bit-Ganzzahlen und Überladungen der Funktion der Basisklasse.  
  
 Stellen Sie sicher, dass Sie überprüfen, die Größe und die Datentypen der Parameter ob, bei der Arbeit mit COM-Objekte. Wenn Sie ein COM-Objekt, die ein Visual Basic 6.0-Auflistungsobjekt als Argument akzeptiert verwenden, können nicht Sie z. B. eine Sammlung aus einer neueren Version von Visual Basic bereitstellen.  
  
 Eigenschaften und Methoden, die von COM-Klassen geerbt können, überschrieben werden dies bedeutet, dass Sie eine lokale Eigenschaft oder Methode, die eine Eigenschaft ersetzt oder von einer COM-Basisklasse geerbten Methode deklarieren können. Die Regeln für das Überschreiben von geerbter Eigenschaften für COM-ähneln den Regeln für das Überschreiben von anderen Eigenschaften und Methoden mit den folgenden Ausnahmen:  
  
-   Wenn Sie eine beliebige Eigenschaft oder Methode, die aus einer COM‑Klasse geerbt überschreiben, müssen Sie alle anderen geerbte Eigenschaften und Methoden überschreiben.  
  
-   Eigenschaften, mit denen `ByRef` Parameter können nicht überschrieben werden.  
  
## <a name="see-also"></a>Siehe auch
- [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
