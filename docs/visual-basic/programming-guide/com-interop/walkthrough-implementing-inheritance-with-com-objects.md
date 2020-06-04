---
title: 'Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: bdb891e1a150f0d7b79aefcc3db1f18dc8e84be4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396726"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="913b2-102">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="913b2-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="913b2-103">Sie können Visual Basic Klassen von `Public` Klassen in COM-Objekten ableiten, auch in früheren Versionen von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="913b2-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="913b2-104">Die Eigenschaften und Methoden von Klassen, die von COM-Objekten geerbt werden, können überschrieben oder überladen werden, auch wenn Eigenschaften und Methoden einer beliebigen anderen Basisklasse überschrieben oder überladen werden können.</span><span class="sxs-lookup"><span data-stu-id="913b2-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="913b2-105">Die Vererbung von COM-Objekten ist nützlich, wenn Sie über eine vorhandene Klassenbibliothek verfügen, die Sie nicht neu kompilieren möchten.</span><span class="sxs-lookup"><span data-stu-id="913b2-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="913b2-106">Im folgenden Verfahren wird gezeigt, wie Sie mit Visual Basic 6,0 ein COM-Objekt erstellen, das eine-Klasse enthält, und dieses dann als Basisklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="913b2-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="913b2-107">So erstellen Sie das COM-Objekt, das in dieser exemplarischen Vorgehensweise verwendet wird</span><span class="sxs-lookup"><span data-stu-id="913b2-107">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="913b2-108">Öffnen Sie in Visual Basic 6,0 ein neues ActiveX-DLL-Projekt.</span><span class="sxs-lookup"><span data-stu-id="913b2-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="913b2-109">Es wird ein Projekt mit dem Namen `Project1` erstellt.</span><span class="sxs-lookup"><span data-stu-id="913b2-109">A project named `Project1` is created.</span></span> <span data-ttu-id="913b2-110">Es verfügt über eine Klasse mit dem Namen `Class1` .</span><span class="sxs-lookup"><span data-stu-id="913b2-110">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="913b2-111">Klicken Sie im **Projekt Explorer**mit der rechten Maustaste auf **Projekt1**, und klicken Sie dann auf **Projekt1 Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="913b2-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="913b2-112">Das Dialogfeld **Projekteigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-112">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="913b2-113">Ändern Sie im Dialogfeld **Projekteigenschaften** auf der Registerkarte **Allgemein** den Projektnamen, indem Sie `ComObject1` im **Feldprojekt Name** eingeben.</span><span class="sxs-lookup"><span data-stu-id="913b2-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="913b2-114">Klicken Sie im **Projekt Explorer**mit der rechten Maustaste auf `Class1` , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="913b2-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="913b2-115">Das Fenster **Eigenschaften** für die-Klasse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-115">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="913b2-116">Ändern Sie die- `Name` Eigenschaft in `MathFunctions` .</span><span class="sxs-lookup"><span data-stu-id="913b2-116">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="913b2-117">Klicken Sie im **Projekt Explorer**mit der rechten Maustaste auf `MathFunctions` , und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="913b2-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="913b2-118">Der **Code-Editor** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-118">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="913b2-119">Fügen Sie eine lokale Variable hinzu, die den Eigenschafts Wert enthält:</span><span class="sxs-lookup"><span data-stu-id="913b2-119">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="913b2-120">Eigenschaften `Let` und Eigenschaften `Get` Prozeduren hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="913b2-120">Add Property `Let` and Property `Get` property procedures:</span></span>

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

9. <span data-ttu-id="913b2-121">Fügen Sie eine Funktion hinzu:</span><span class="sxs-lookup"><span data-stu-id="913b2-121">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="913b2-122">Erstellen und registrieren Sie das COM-Objekt, indem Sie im Menü **Datei** auf **ComObject1. dll** festlegen klicken.</span><span class="sxs-lookup"><span data-stu-id="913b2-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="913b2-123">Obwohl Sie eine mit Visual Basic erstellte Klasse auch als COM-Objekt verfügbar machen können, handelt es sich nicht um ein echtes com-Objekt, das in dieser exemplarischen Vorgehensweise nicht verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="913b2-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="913b2-124">Weitere Informationen finden Sie unter [com-Interoperabilität in .NET Framework Anwendungen](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="913b2-124">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="913b2-125">Interopassemblys</span><span class="sxs-lookup"><span data-stu-id="913b2-125">Interop Assemblies</span></span>

<span data-ttu-id="913b2-126">Im folgenden Verfahren erstellen Sie eine Interop-Assembly, die als Brücke zwischen nicht verwaltetem Code (z. b. einem COM-Objekt) und dem verwalteten Code, der von Visual Studio verwendet wird, fungiert.</span><span class="sxs-lookup"><span data-stu-id="913b2-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="913b2-127">Die Interop-Assembly, die Visual Basic erstellt, verarbeitet viele Details der Arbeit mit COM-Objekten, z. b. *Interop*-Marshalling, das Packen von Parametern und Rückgabe Werten in äquivalente Datentypen beim Wechsel zu und von COM-Objekten.</span><span class="sxs-lookup"><span data-stu-id="913b2-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="913b2-128">Der Verweis in der Visual Basic Anwendung verweist auf die Interop-Assembly, nicht auf das tatsächliche com-Objekt.</span><span class="sxs-lookup"><span data-stu-id="913b2-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="913b2-129">So verwenden Sie ein COM-Objekt mit Visual Basic 2005 und höheren Versionen</span><span class="sxs-lookup"><span data-stu-id="913b2-129">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="913b2-130">Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="913b2-130">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="913b2-131">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="913b2-131">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="913b2-132">Das Dialogfeld **Verweis hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-132">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="913b2-133">Doppelklicken **COM** Sie auf der Registerkarte com `ComObject1` in die Liste **Komponenten Name** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="913b2-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="913b2-134">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="913b2-134">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="913b2-135">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-135">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="913b2-136">Klicken Sie im Bereich **Vorlagen** auf **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="913b2-136">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="913b2-137">Der Standard Dateiname, `Class1.vb` , wird im Feld **Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="913b2-138">Ändern Sie dieses Feld in MathClass. vb, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="913b2-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="913b2-139">Dadurch wird eine Klasse mit `MathClass` dem Namen erstellt und der zugehörige Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-139">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="913b2-140">Fügen Sie den folgenden Code am Anfang von ein `MathClass` , um von der com-Klasse zu erben.</span><span class="sxs-lookup"><span data-stu-id="913b2-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="913b2-141">Überladen Sie die öffentliche Methode der Basisklasse, indem Sie folgenden Code hinzufügen `MathClass` :</span><span class="sxs-lookup"><span data-stu-id="913b2-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="913b2-142">Erweitern Sie die geerbte Klasse, indem Sie folgenden Code hinzufügen `MathClass` :</span><span class="sxs-lookup"><span data-stu-id="913b2-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="913b2-143">Die neue Klasse erbt die Eigenschaften der Basisklasse im COM-Objekt, über lädt eine-Methode und definiert eine neue-Methode, um die-Klasse zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="913b2-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

### <a name="to-test-the-inherited-class"></a><span data-ttu-id="913b2-144">So testen Sie die geerbte Klasse</span><span class="sxs-lookup"><span data-stu-id="913b2-144">To test the inherited class</span></span>

1. <span data-ttu-id="913b2-145">Fügen Sie dem Start Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="913b2-145">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="913b2-146">`Click`Fügen Sie den folgenden Code in die Ereignishandlerprozedur der Schaltfläche ein, um eine Instanz von zu erstellen `MathClass` und die überladenen Methoden aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="913b2-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="913b2-147">Führen Sie das Projekt aus, indem Sie F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="913b2-147">Run the project by pressing F5.</span></span>

<span data-ttu-id="913b2-148">Wenn Sie im Formular auf die Schaltfläche klicken, `AddNumbers` wird die-Methode zuerst mit `Short` Datentyp Nummern aufgerufen, und Visual Basic wählt die entsprechende Methode aus der Basisklasse aus.</span><span class="sxs-lookup"><span data-stu-id="913b2-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="913b2-149">Der zweite aufrufen `AddNumbers` von wird an die Überladungs Methode aus geleitet `MathClass` .</span><span class="sxs-lookup"><span data-stu-id="913b2-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="913b2-150">Der dritte Aufruf ruft die- `SubtractNumbers` Methode auf, die die-Klasse erweitert.</span><span class="sxs-lookup"><span data-stu-id="913b2-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="913b2-151">Die-Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="913b2-151">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="913b2-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="913b2-152">Next Steps</span></span>

<span data-ttu-id="913b2-153">Möglicherweise haben Sie bemerkt, dass die überladene `AddNumbers` Funktion den gleichen Datentyp wie die Methode hat, die von der Basisklasse des COM-Objekts geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="913b2-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="913b2-154">Dies liegt daran, dass die Argumente und Parameter der Basisklassen Methode in Visual Basic 6,0 als 16-Bit-Ganzzahlen definiert sind, jedoch `Short` in späteren Versionen von Visual Basic als 16-Bit-Ganzzahlen vom Typ verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="913b2-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="913b2-155">Die neue Funktion akzeptiert ganzzahlige 32-Bit-Werte und über lädt die Basisklassen Funktion.</span><span class="sxs-lookup"><span data-stu-id="913b2-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="913b2-156">Stellen Sie beim Arbeiten mit COM-Objekten sicher, dass Sie die Größe und die Datentypen von Parametern überprüfen.</span><span class="sxs-lookup"><span data-stu-id="913b2-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="913b2-157">Wenn Sie z. b. ein COM-Objekt verwenden, das ein Visual Basic 6,0-Auflistungs Objekt als Argument akzeptiert, können Sie keine Auflistung aus einer neueren Version von Visual Basic bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="913b2-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="913b2-158">Eigenschaften und Methoden, die von COM-Klassen geerbt werden, können überschrieben werden. Dies bedeutet, dass Sie eine lokale Eigenschaft oder Methode deklarieren können, die eine von einer com-Basisklasse geerbte Eigenschaft oder Methode ersetzt.</span><span class="sxs-lookup"><span data-stu-id="913b2-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="913b2-159">Die Regeln zum Überschreiben von geerbten com-Eigenschaften ähneln den Regeln zum Überschreiben anderer Eigenschaften und Methoden mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="913b2-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="913b2-160">Wenn Sie eine Eigenschaft oder Methode überschreiben, die von einer com-Klasse geerbt wird, müssen Sie alle anderen geerbten Eigenschaften und Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="913b2-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="913b2-161">Eigenschaften, die `ByRef` Parameter verwenden, können nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="913b2-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="913b2-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="913b2-162">See also</span></span>

- [<span data-ttu-id="913b2-163">COM-Interoperabilität in .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="913b2-163">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="913b2-164">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="913b2-164">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="913b2-165">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="913b2-165">Short Data Type</span></span>](../../language-reference/data-types/short-data-type.md)
