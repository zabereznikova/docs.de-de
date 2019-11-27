---
title: 'Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 209e1005b9f944bf4883e8406031fb17d4d60df1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347989"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic)

Sie können Visual Basic Klassen von `Public` Klassen in COM-Objekten ableiten, auch in früheren Versionen von Visual Basic. Die Eigenschaften und Methoden von Klassen, die von COM-Objekten geerbt werden, können überschrieben oder überladen werden, auch wenn Eigenschaften und Methoden einer beliebigen anderen Basisklasse überschrieben oder überladen werden können. Die Vererbung von COM-Objekten ist nützlich, wenn Sie über eine vorhandene Klassenbibliothek verfügen, die Sie nicht neu kompilieren möchten.

Im folgenden Verfahren wird gezeigt, wie Sie mit Visual Basic 6,0 ein COM-Objekt erstellen, das eine-Klasse enthält, und dieses dann als Basisklasse verwenden.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>So erstellen Sie das COM-Objekt, das in dieser exemplarischen Vorgehensweise verwendet wird

1. Öffnen Sie in Visual Basic 6,0 ein neues ActiveX-DLL-Projekt. Ein Projekt mit dem Namen `Project1` wird erstellt. Es verfügt über eine Klasse mit dem Namen `Class1`.

2. Klicken Sie im **Projekt Explorer**mit der rechten Maustaste auf **Projekt1**, und klicken Sie dann auf **Projekt1 Eigenschaften**. Das Dialogfeld **Projekteigenschaften** wird angezeigt.

3. Ändern Sie im Dialogfeld **Projekteigenschaften** auf der Registerkarte **Allgemein** den Projektnamen, indem Sie im Feld **Projektname** `ComObject1` eingeben.

4. Klicken Sie im **Projekt Explorer**mit der rechten Maustaste auf `Class1`, und klicken Sie dann auf **Eigenschaften**. Das Fenster **Eigenschaften** für die-Klasse wird angezeigt.

5. Ändern Sie die `Name`-Eigenschaft in `MathFunctions`.

6. Klicken Sie im **Projekt Explorer**mit der rechten Maustaste auf `MathFunctions`, und klicken Sie dann auf **Code anzeigen**. Der **Code-Editor** wird angezeigt.

7. Fügen Sie eine lokale Variable hinzu, die den Eigenschafts Wert enthält:

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. Eigenschaften `Let` und Eigenschaften `Get` Eigenschaften Prozeduren hinzufügen:

    ```vb
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

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. Erstellen und registrieren Sie das COM-Objekt, indem Sie im Menü **Datei** auf **ComObject1. dll** festlegen klicken.

    > [!NOTE]
    > Obwohl Sie eine mit Visual Basic erstellte Klasse auch als COM-Objekt verfügbar machen können, handelt es sich nicht um ein echtes com-Objekt, das in dieser exemplarischen Vorgehensweise nicht verwendet werden kann. Weitere Informationen finden Sie unter [com-Interoperabilität in .NET Framework Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).

## <a name="interop-assemblies"></a>Interopassemblys

Im folgenden Verfahren erstellen Sie eine Interop-Assembly, die als Brücke zwischen nicht verwaltetem Code (z. b. einem COM-Objekt) und dem verwalteten Code, der von Visual Studio verwendet wird, fungiert. Die Interop-Assembly, die Visual Basic erstellt, verarbeitet viele Details der Arbeit mit COM-Objekten, z. b. *Interop*-Marshalling, das Packen von Parametern und Rückgabe Werten in äquivalente Datentypen beim Wechsel zu und von COM-Objekten. Der Verweis in der Visual Basic Anwendung verweist auf die Interop-Assembly, nicht auf das tatsächliche com-Objekt.

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>So verwenden Sie ein COM-Objekt mit Visual Basic 2005 und höheren Versionen

1. Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.

2. Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .

     Das Dialogfeld **Verweis hinzufügen** wird angezeigt.

3. Doppelklicken Sie auf der Registerkarte **com** auf `ComObject1` in der Liste **Komponenten Name** , und klicken Sie dann auf **OK**.

4. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.

     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.

5. Klicken Sie im Bereich **Vorlagen** auf **Klasse**.

     Der Standard Dateiname `Class1.vb`wird im Feld **Name** angezeigt. Ändern Sie dieses Feld in MathClass. vb, und klicken Sie auf **Hinzufügen**. Dadurch wird eine Klasse mit dem Namen `MathClass`erstellt und der zugehörige Code angezeigt.

6. Fügen Sie den folgenden Code am Anfang der `MathClass` ein, um von der com-Klasse zu erben.

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. Überladen Sie die öffentliche Methode der Basisklasse, indem Sie den folgenden Code `MathClass`hinzufügen:

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. Erweitern Sie die geerbte Klasse, indem Sie den folgenden Code `MathClass`hinzufügen:

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

Die neue Klasse erbt die Eigenschaften der Basisklasse im COM-Objekt, über lädt eine-Methode und definiert eine neue-Methode, um die-Klasse zu erweitern.

### <a name="to-test-the-inherited-class"></a>So testen Sie die geerbte Klasse

1. Fügen Sie dem Start Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code anzuzeigen.

2. Fügen Sie in der `Click`-Ereignishandlerprozedur der Schaltfläche den folgenden Code hinzu, um eine Instanz `MathClass` zu erstellen und die überladenen Methoden aufzurufen:

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. Führen Sie das Projekt aus, indem Sie F5 drücken.

Wenn Sie auf die Schaltfläche im Formular klicken, wird zuerst die `AddNumbers`-Methode mit `Short` Datentyp Nummern aufgerufen, und Visual Basic wählt die entsprechende Methode aus der Basisklasse aus. Der zweite `AddNumbers` aufrufen wird von `MathClass`an die Überladungs Methode geleitet. Der dritte Aufruf ruft die `SubtractNumbers`-Methode auf, die die-Klasse erweitert. Die-Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.

## <a name="next-steps"></a>Nächste Schritte

Möglicherweise haben Sie bemerkt, dass die überladene `AddNumbers`-Funktion den gleichen Datentyp wie die Methode hat, die von der Basisklasse des COM-Objekts geerbt wurde. Dies liegt daran, dass die Argumente und Parameter der Basisklassen Methode in Visual Basic 6,0 als 16-Bit-Ganzzahlen definiert sind, jedoch in späteren Versionen von Visual Basic als 16-Bit-Ganzzahlen vom Typ `Short` verfügbar gemacht werden. Die neue Funktion akzeptiert ganzzahlige 32-Bit-Werte und über lädt die Basisklassen Funktion.

Stellen Sie beim Arbeiten mit COM-Objekten sicher, dass Sie die Größe und die Datentypen von Parametern überprüfen. Wenn Sie z. b. ein COM-Objekt verwenden, das ein Visual Basic 6,0-Auflistungs Objekt als Argument akzeptiert, können Sie keine Auflistung aus einer neueren Version von Visual Basic bereitstellen.

Eigenschaften und Methoden, die von COM-Klassen geerbt werden, können überschrieben werden. Dies bedeutet, dass Sie eine lokale Eigenschaft oder Methode deklarieren können, die eine von einer com-Basisklasse geerbte Eigenschaft oder Methode ersetzt. Die Regeln zum Überschreiben von geerbten com-Eigenschaften ähneln den Regeln zum Überschreiben anderer Eigenschaften und Methoden mit den folgenden Ausnahmen:

- Wenn Sie eine Eigenschaft oder Methode überschreiben, die von einer com-Klasse geerbt wird, müssen Sie alle anderen geerbten Eigenschaften und Methoden überschreiben.

- Eigenschaften, die `ByRef`-Parameter verwenden, können nicht überschrieben werden.

## <a name="see-also"></a>Siehe auch

- [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
