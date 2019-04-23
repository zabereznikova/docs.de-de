---
title: 'Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekte (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 0b3977e73e3b2aa9e80e2dab08d15035283b8387
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334145"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="94a43-102">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94a43-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="94a43-103">Sie können aus Visual Basic-Klassen ableiten `Public` Klassen in COM-Objekte, auch solche, die in früheren Versionen von Visual Basic erstellt.</span><span class="sxs-lookup"><span data-stu-id="94a43-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="94a43-104">Die Eigenschaften und Methoden von Klassen geerbt von COM-Objekte können überschrieben oder überladen werden, wie Eigenschaften und Methoden von einer anderen Basisklasse überschrieben oder überladen werden können.</span><span class="sxs-lookup"><span data-stu-id="94a43-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="94a43-105">Vererbung von COM-Objekten ist nützlich, wenn Sie eine vorhandene Klassenbibliothek verfügen, die nicht neu kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="94a43-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="94a43-106">Das folgende Verfahren zeigt, wie Visual Basic 6.0 verwenden, um ein COM-Objekt zu erstellen, die eine Klasse enthält, und klicken Sie dann als Basisklasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="94a43-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="94a43-107">Das COM-Objekt zu erstellen, das in dieser exemplarischen Vorgehensweise verwendet wird</span><span class="sxs-lookup"><span data-stu-id="94a43-107">To build the COM object that is used in this walkthrough</span></span>  
  
1. <span data-ttu-id="94a43-108">Öffnen Sie in Visual Basic 6.0 ein neues ActiveX DLL-Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="94a43-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="94a43-109">Ein Projekt namens `Project1` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94a43-109">A project named `Project1` is created.</span></span> <span data-ttu-id="94a43-110">Es wurde eine Klasse namens `Class1`.</span><span class="sxs-lookup"><span data-stu-id="94a43-110">It has a class named `Class1`.</span></span>  
  
2. <span data-ttu-id="94a43-111">In der **Projektexplorer**, mit der rechten Maustaste **Projekt1**, und klicken Sie dann auf **Projekt1 Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="94a43-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="94a43-112">Die **Projekteigenschaften** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3. <span data-ttu-id="94a43-113">Auf der **allgemeine** Registerkarte die **Projekteigenschaften** Dialogfeld ändern den Namen des Projekts durch Eingabe `ComObject1` in die **Projektname** Feld.</span><span class="sxs-lookup"><span data-stu-id="94a43-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4. <span data-ttu-id="94a43-114">In der **Projektexplorer**, mit der rechten Maustaste `Class1`, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="94a43-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="94a43-115">Die **Eigenschaften** Fenster für die Klasse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-115">The **Properties** window for the class is displayed.</span></span>  
  
5. <span data-ttu-id="94a43-116">Ändern der `Name` Eigenschaft `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="94a43-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6. <span data-ttu-id="94a43-117">In der **Projektexplorer**, mit der rechten Maustaste `MathFunctions`, und klicken Sie dann auf **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="94a43-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="94a43-118">Die **Code-Editor** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-118">The **Code Editor** is displayed.</span></span>  
  
7. <span data-ttu-id="94a43-119">Fügen Sie eine lokale Variable für den Wert der Eigenschaft hinzu:</span><span class="sxs-lookup"><span data-stu-id="94a43-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8. <span data-ttu-id="94a43-120">Fügen Sie Eigenschaft `Let` und `Get` Property-Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="94a43-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="94a43-121">Fügen Sie eine Funktion hinzu:</span><span class="sxs-lookup"><span data-stu-id="94a43-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="94a43-122">Erstellen und registrieren Sie das COM-Objekt, indem Sie auf **stellen ComObject1.dll** auf die **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="94a43-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="94a43-123">Obwohl Sie auch eine Klasse erstellt, die mit Visual Basic als COM-Objekt verfügbar machen können, ist nicht "true" COM-Objekt und kann nicht in dieser exemplarischen Vorgehensweise verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94a43-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="94a43-124">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="94a43-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="94a43-125">Interop-Assemblys</span><span class="sxs-lookup"><span data-stu-id="94a43-125">Interop Assemblies</span></span>  
 <span data-ttu-id="94a43-126">Im folgenden Verfahren erstellen Sie eine interop-Assembly, fungiert als Brücke zwischen nicht verwalteten Code (z. B. ein COM-Objekt) und verwaltetem Code von den Visual Studio verwendet.</span><span class="sxs-lookup"><span data-stu-id="94a43-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="94a43-127">Die Interop-Assembly, die Visual Basic erstellt behandelt viele der Details für die Arbeit mit COM-Objekten, z. B. *interop-Marshalling*, der Prozess der paketerstellung-Parameter und Rückgabewerte in äquivalente Typen wie verschoben werden und von COM-Objekten.</span><span class="sxs-lookup"><span data-stu-id="94a43-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="94a43-128">Der Verweis in Visual Basic-Anwendung verweist auf die interop-Assembly, nicht die tatsächliche COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="94a43-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="94a43-129">Ein COM-Objekt mit Visual Basic 2005 und höheren Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="94a43-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1. <span data-ttu-id="94a43-130">Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="94a43-130">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="94a43-131">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="94a43-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="94a43-132">Das Dialogfeld **Verweis hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3. <span data-ttu-id="94a43-133">Auf der **COM** Registerkarte, doppelklicken Sie auf `ComObject1` in die **Komponentenname** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94a43-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4. <span data-ttu-id="94a43-134">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="94a43-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="94a43-135">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5. <span data-ttu-id="94a43-136">In der **Vorlagen** Bereich, klicken Sie auf **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="94a43-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="94a43-137">Der Standarddateiname, `Class1.vb`, wird in der **Namen** Feld.</span><span class="sxs-lookup"><span data-stu-id="94a43-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="94a43-138">Ändern Sie dieses Feld MathClass.vb, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="94a43-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="94a43-139">Dies erstellt eine Klasse namens `MathClass`, und ihr Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6. <span data-ttu-id="94a43-140">Fügen Sie den folgenden Code am Anfang `MathClass` von COM-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="94a43-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]  
  
7. <span data-ttu-id="94a43-141">Überladen Sie die öffentliche Methode der Basisklasse durch den folgenden Code hinzufügen `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="94a43-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]  
  
8. <span data-ttu-id="94a43-142">Die geerbte Klasse erweitern, indem Sie den folgenden Code hinzufügen `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="94a43-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]  
  
 <span data-ttu-id="94a43-143">Die neue Klasse erbt die Eigenschaften der Basisklasse in das COM-Objekt, Überladungen eine Methode und eine neue Methode zum Erweitern Sie die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="94a43-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="94a43-144">Um die geerbte Klasse zu testen.</span><span class="sxs-lookup"><span data-stu-id="94a43-144">To test the inherited class</span></span>  
  
1. <span data-ttu-id="94a43-145">Das Startformular fügen Sie eine Schaltfläche hinzu, und doppelklicken Sie darauf, um ihren Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="94a43-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2. <span data-ttu-id="94a43-146">In der Schaltfläche `Click` Ereignishandlerprozedur, fügen Sie den folgenden Code zum Erstellen einer Instanz von `MathClass` die überladenen Methoden aufrufen:</span><span class="sxs-lookup"><span data-stu-id="94a43-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]  
  
3. <span data-ttu-id="94a43-147">Führen Sie das Projekt durch Drücken von F5.</span><span class="sxs-lookup"><span data-stu-id="94a43-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="94a43-148">Beim Anklicken der Schaltfläche im Formular die `AddNumbers` -Methode zuerst aufgerufen, wobei `Short` Daten geben Sie Zahlen ein, und Visual Basic wählt die entsprechende Methode aus der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="94a43-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="94a43-149">Der zweite Aufruf von `AddNumbers` gesteuert wird, um die überladene Methode von `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="94a43-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="94a43-150">Die dritte Aufrufe der `SubtractNumbers` -Methode, die die Klasse erweitert.</span><span class="sxs-lookup"><span data-stu-id="94a43-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="94a43-151">Die Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94a43-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="94a43-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="94a43-152">Next Steps</span></span>  
 <span data-ttu-id="94a43-153">Sie haben vielleicht festgestellt, die den überladenen `AddNumbers` Funktion angezeigt wird, um den gleichen Datentyp wie die von der Basisklasse des COM-Objekts geerbte Methode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="94a43-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="94a43-154">Dies ist, da die Argumente und Parameter der Methode der Basisklasse als 16-Bit-Ganzzahlen in Visual Basic 6.0 definiert sind, aber sie werden als 16-Bit-Ganzzahlen vom Typ verfügbar gemacht `Short` in höheren Versionen von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="94a43-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="94a43-155">Die neue Funktion akzeptiert die 32-Bit-Ganzzahlen und Überladungen der Funktion der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="94a43-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="94a43-156">Stellen Sie sicher, dass Sie überprüfen, die Größe und die Datentypen der Parameter ob, bei der Arbeit mit COM-Objekte.</span><span class="sxs-lookup"><span data-stu-id="94a43-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="94a43-157">Wenn Sie ein COM-Objekt, die ein Visual Basic 6.0-Auflistungsobjekt als Argument akzeptiert verwenden, können nicht Sie z. B. eine Sammlung aus einer neueren Version von Visual Basic bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="94a43-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="94a43-158">Eigenschaften und Methoden, die von COM-Klassen geerbt können, überschrieben werden dies bedeutet, dass Sie eine lokale Eigenschaft oder Methode, die eine Eigenschaft ersetzt oder von einer COM-Basisklasse geerbten Methode deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="94a43-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="94a43-159">Die Regeln für das Überschreiben von geerbter Eigenschaften für COM-ähneln den Regeln für das Überschreiben von anderen Eigenschaften und Methoden mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="94a43-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="94a43-160">Wenn Sie eine beliebige Eigenschaft oder Methode, die aus einer COM‑Klasse geerbt überschreiben, müssen Sie alle anderen geerbte Eigenschaften und Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="94a43-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="94a43-161">Eigenschaften, mit denen `ByRef` Parameter können nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="94a43-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a43-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a43-162">See also</span></span>

- [<span data-ttu-id="94a43-163">COM-Interoperabilität in .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="94a43-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="94a43-164">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="94a43-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="94a43-165">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="94a43-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
