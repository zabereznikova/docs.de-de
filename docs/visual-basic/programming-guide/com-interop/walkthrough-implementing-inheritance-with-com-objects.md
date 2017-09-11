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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0e816d1728678467d930de524b894d175f9b0c0a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="6beaf-102">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6beaf-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="6beaf-103">Sie können von Visual Basic-Klassen ableiten `Public` Klassen in COM-Objekte, auch solche, die in früheren Versionen erstellten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6beaf-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="6beaf-104">Die Eigenschaften und Methoden von Klassen geerbt von COM-Objekte können überschrieben oder überladen, wie Eigenschaften und Methoden jeder anderen Basisklasse überschrieben oder überladen werden können.</span><span class="sxs-lookup"><span data-stu-id="6beaf-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="6beaf-105">Vererbung von COM-Objekten ist nützlich, wenn Sie eine vorhandene Klassenbibliothek verfügen, die nicht neu kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6beaf-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="6beaf-106">Das folgende Verfahren veranschaulicht, wie Visual Basic 6.0 verwenden, um ein COM-Objekt zu erstellen, die eine Klasse enthält, und dann als Basisklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="6beaf-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="6beaf-107">Das COM-Objekt zu erstellen, das in dieser exemplarischen Vorgehensweise verwendet wird</span><span class="sxs-lookup"><span data-stu-id="6beaf-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="6beaf-108">Öffnen Sie in Visual Basic 6.0 ein neues ActiveX DLL-Projekt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="6beaf-109">Ein Projekt namens `Project1` wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-109">A project named `Project1` is created.</span></span> <span data-ttu-id="6beaf-110">Eine Klasse mit dem Namen `Class1`.</span><span class="sxs-lookup"><span data-stu-id="6beaf-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="6beaf-111">In der **Projekt-Explorer**, mit der rechten Maustaste **Project1**, und klicken Sie dann auf **Eigenschaften von Project1**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="6beaf-112">Die **Projekteigenschaften** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="6beaf-113">Auf der **allgemeine** auf der Registerkarte der **Projekteigenschaften** Dialogfeld ändern den Namen des Projekts durch Eingabe `ComObject1` in der **Projektname** Feld.</span><span class="sxs-lookup"><span data-stu-id="6beaf-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="6beaf-114">In der **Projekt-Explorer**, mit der rechten Maustaste `Class1`, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="6beaf-115">Die **Eigenschaften** für die Klasse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="6beaf-116">Ändern der `Name` -Eigenschaft `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="6beaf-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="6beaf-117">In der **Projekt-Explorer**, mit der rechten Maustaste `MathFunctions`, und klicken Sie dann auf **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="6beaf-118">Die **Code-Editor** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="6beaf-119">Fügen Sie eine lokale Variable den Wert der Eigenschaft hinzu:</span><span class="sxs-lookup"><span data-stu-id="6beaf-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="6beaf-120">Fügen Sie die Eigenschaft `Let` und `Get` Eigenschaftenprozeduren:</span><span class="sxs-lookup"><span data-stu-id="6beaf-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="6beaf-121">Fügen Sie eine Funktion hinzu:</span><span class="sxs-lookup"><span data-stu-id="6beaf-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="6beaf-122">Erstellen und registrieren Sie das COM-Objekt, indem Sie auf **stellen ComObject1.dll** auf der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="6beaf-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6beaf-123">Obwohl Sie auch eine mit erstellte Klasse verfügbar gemacht werden können [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] als COM-Objekt ist ein echtes COM-Objekt und kann nicht in dieser exemplarischen Vorgehensweise verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6beaf-123">Although you can also expose a class created with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="6beaf-124">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="6beaf-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="6beaf-125">Interop-Assemblys</span><span class="sxs-lookup"><span data-stu-id="6beaf-125">Interop Assemblies</span></span>  
 <span data-ttu-id="6beaf-126">In der folgenden Prozedur erstellen Sie eine Interop-Assembly, die fungiert als Brücke zwischen nicht verwaltetem Code (z. B. ein COM-Objekt) und verwaltetem Code [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="6beaf-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] uses.</span></span> <span data-ttu-id="6beaf-127">Die Interop-Assembly, die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] viele Details der Arbeit mit COM-Objekten, z. B. Handles erstellt *Interop-Marshalling*, der Prozess Zusammenfassen von Parametern und Rückgabewerten in äquivalente Typen, wie sie die an und von COM-Objekten wechseln.</span><span class="sxs-lookup"><span data-stu-id="6beaf-127">The interop assembly that [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="6beaf-128">Der Verweis in der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verweist auf die Interop-Assembly, nicht auf das eigentliche COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-128">The reference in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="6beaf-129">Ein COM-Objekt mit Visual Basic 2005 und höheren Versionen verwenden</span><span class="sxs-lookup"><span data-stu-id="6beaf-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="6beaf-130">Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-130">Open a new [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="6beaf-131">Auf der **Projekt** Menü klicken Sie auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="6beaf-132">Die **Verweis hinzufügen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="6beaf-133">Auf der **COM** Registerkarte, doppelklicken Sie auf `ComObject1` in der **Komponentenname** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="6beaf-134">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="6beaf-135">Die **neues Element hinzufügen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="6beaf-136">In der **Vorlagen** Bereich, klicken Sie auf **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="6beaf-137">Der Standarddateiname `Class1.vb`, wird in der **Namen** Feld.</span><span class="sxs-lookup"><span data-stu-id="6beaf-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="6beaf-138">Ändern Sie dieses Feld in MathClass.vb, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6beaf-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="6beaf-139">Dadurch wird eine Klasse namens `MathClass`, und ihr Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="6beaf-140">Fügen Sie den folgenden Code am Anfang der `MathClass` von COM-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="6beaf-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     <span data-ttu-id="6beaf-141">[!code-vb[VbVbalrInterop&#31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6beaf-141">[!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span></span>  
  
7.  <span data-ttu-id="6beaf-142">Überladen Sie die öffentliche Methode der Basisklasse durch den folgenden Code hinzufügen `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="6beaf-142">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="6beaf-143">[!code-vb[VbVbalrInterop&#32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="6beaf-143">[!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span></span>  
  
8.  <span data-ttu-id="6beaf-144">Die geerbte Klasse erweitern, indem Sie den folgenden Code hinzufügen `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="6beaf-144">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="6beaf-145">[!code-vb[VbVbalrInterop&33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="6beaf-145">[!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span></span>  
  
 <span data-ttu-id="6beaf-146">Die neue Klasse erbt die Eigenschaften der Basisklasse im COM-Objekt, überlädt eine Methode und definiert eine neue Methode, um die Klasse zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6beaf-146">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="6beaf-147">So testen Sie die geerbte Klasse</span><span class="sxs-lookup"><span data-stu-id="6beaf-147">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="6beaf-148">Dem Startformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um ihren Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6beaf-148">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="6beaf-149">Die Schaltfläche `Click` Handler Ereignisprozedur, fügen Sie folgenden Code zum Erstellen einer Instanz von `MathClass` und die überladenen Methoden aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="6beaf-149">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     <span data-ttu-id="6beaf-150">[!code-vb[VbVbalrInterop&#34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="6beaf-150">[!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span></span>  
  
3.  <span data-ttu-id="6beaf-151">Führen Sie das Projekt, indem Sie F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="6beaf-151">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="6beaf-152">Beim Anklicken der Schaltfläche auf dem Formular die `AddNumbers` -Methode zuerst aufgerufen wird und `Short` Datentyp Zahlen und [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wählt die entsprechende Methode der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="6beaf-152">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chooses the appropriate method from the base class.</span></span> <span data-ttu-id="6beaf-153">Der zweite Aufruf von `AddNumbers` wird angewiesen, die überladene Methode von `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="6beaf-153">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="6beaf-154">Die dritte aufrufen, ruft die `SubtractNumbers` -Methode, die die Klasse erweitert.</span><span class="sxs-lookup"><span data-stu-id="6beaf-154">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="6beaf-155">Die Eigenschaft in der Basisklasse wird festgelegt, und der Wert wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-155">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6beaf-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6beaf-156">Next Steps</span></span>  
 <span data-ttu-id="6beaf-157">Sie haben möglicherweise bemerkt, die überladenen `AddNumbers` -Funktion hat den gleichen Datentyp wie die von der Basisklasse des COM-Objekts geerbte Methode.</span><span class="sxs-lookup"><span data-stu-id="6beaf-157">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="6beaf-158">Dies wird als 16-Bit-Ganzzahlen vom Typ verfügbar gemacht werden, da die Argumente und Parameter der Methode der Basisklasse werden als 16-Bit-Ganzzahlen in Visual Basic 6.0 definiert `Short` in höheren Versionen von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6beaf-158">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="6beaf-159">Die neue Funktion akzeptiert 32-Bit-Ganzzahlen und Funktion der Basisklasse überlädt.</span><span class="sxs-lookup"><span data-stu-id="6beaf-159">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="6beaf-160">Bei der Arbeit mit COM-Objekte stellen Sie sicher, dass Sie die Größe und die Datentypen der Parameter überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6beaf-160">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="6beaf-161">Wenn Sie ein COM-Objekt, das ein Visual Basic 6.0-Auflistungsobjekt als Argument akzeptiert verwenden, können nicht Sie z. B. eine Sammlung aus einer höheren Version von Visual Basic bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6beaf-161">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="6beaf-162">Eigenschaften und Methoden, die von COM-Klassen geerbt können überschrieben werden dies bedeutet, dass Sie eine lokale Eigenschaft oder Methode, die eine Eigenschaft ersetzt oder von einer COM-Basisklasse geerbten Methode deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="6beaf-162">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="6beaf-163">Die Regeln für das Überschreiben von geerbter COM‑Eigenschaften ähneln denen für das Überschreiben anderer Eigenschaften und Methoden mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="6beaf-163">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="6beaf-164">Wenn Sie eine Eigenschaft oder Methode geerbt von einer COM-Klasse überschreiben, müssen Sie alle anderen geerbten Eigenschaften und Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6beaf-164">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="6beaf-165">Eigenschaften, mit denen `ByRef` Parameter können nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6beaf-165">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6beaf-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6beaf-166">See Also</span></span>  
 <span data-ttu-id="6beaf-167">[COM-Interoperabilität in .NET Framework-Clientanwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="6beaf-167">[COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="6beaf-168"> [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="6beaf-168"> [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="6beaf-169"> [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="6beaf-169"> [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)</span></span>
