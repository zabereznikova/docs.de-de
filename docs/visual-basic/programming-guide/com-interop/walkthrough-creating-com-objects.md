---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 5d00aff07358a0c40159fde9c12c70e0842d848b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338619"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="82ff9-102">Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82ff9-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="82ff9-103">Beim Erstellen neuer Anwendungen oder Komponenten empfiehlt es sich, .NET Framework Assemblys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="82ff9-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="82ff9-104">Visual Basic ist es jedoch auch einfach, eine .NET Framework Komponente für com verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="82ff9-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="82ff9-105">Dies ermöglicht es Ihnen, neue Komponenten für frühere Anwendungs Suites bereitzustellen, die COM-Komponenten erfordern.</span><span class="sxs-lookup"><span data-stu-id="82ff9-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="82ff9-106">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit Visual Basic .NET Framework-Objekte als COM-Objekte verfügbar machen, sowohl mit als auch ohne die com-Klassen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="82ff9-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="82ff9-107">Die einfachste Möglichkeit, com-Objekte verfügbar zu machen, ist die Verwendung der com-Klassen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="82ff9-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="82ff9-108">Die com-Klassen Vorlage erstellt eine neue Klasse und konfiguriert dann das Projekt, um die Klasse und die Interoperabilitäts Schicht als COM-Objekt zu generieren und Sie beim Betriebssystem zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="82ff9-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82ff9-109">Obwohl Sie eine Klasse, die in Visual Basic erstellt wurde, auch als COM-Objekt für nicht verwalteten Code verfügbar machen können, handelt es sich nicht um ein echtes com-Objekt, das nicht von Visual Basic verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="82ff9-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="82ff9-110">Weitere Informationen finden Sie unter [com-Interoperabilität in .NET Framework Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="82ff9-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="82ff9-111">So erstellen Sie ein COM-Objekt mithilfe der com-Klassen Vorlage</span><span class="sxs-lookup"><span data-stu-id="82ff9-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="82ff9-112">Öffnen Sie über das Menü **Datei** ein neues Windows-Anwendungsprojekt, indem Sie auf **Neues Projekt**klicken.</span><span class="sxs-lookup"><span data-stu-id="82ff9-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="82ff9-113">Überprüfen Sie im Dialogfeld **Neues Projekt** unter dem Feld **Projekttypen** , ob Windows ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="82ff9-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="82ff9-114">Wählen Sie in der Liste **Vorlagen** die Option **Klassenbibliothek** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="82ff9-115">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82ff9-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="82ff9-116">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="82ff9-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="82ff9-117">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82ff9-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="82ff9-118">Wählen Sie **com-Klasse** aus der Liste **Vorlagen** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="82ff9-119">Visual Basic fügt eine neue Klasse hinzu und konfiguriert das neue Projekt für COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="82ff9-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="82ff9-120">Fügen Sie der com-Klasse Code hinzu, z. b. Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="82ff9-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="82ff9-121">Wählen Sie im Menü **Erstellen** die Option **Build ClassLibrary1** aus.</span><span class="sxs-lookup"><span data-stu-id="82ff9-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="82ff9-122">Visual Basic erstellt die Assembly und registriert das COM-Objekt beim Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="82ff9-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="82ff9-123">Erstellen von COM-Objekten ohne die com-Klassen Vorlage</span><span class="sxs-lookup"><span data-stu-id="82ff9-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="82ff9-124">Sie können eine COM-Klasse auch manuell erstellen, anstatt die com-Klassen Vorlage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="82ff9-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="82ff9-125">Diese Vorgehensweise ist hilfreich, wenn Sie über die Befehlszeile arbeiten oder wenn Sie mehr Kontrolle darüber haben möchten, wie COM-Objekte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="82ff9-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="82ff9-126">So richten Sie das Projekt ein, um ein COM-Objekt zu generieren</span><span class="sxs-lookup"><span data-stu-id="82ff9-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="82ff9-127">Öffnen Sie über das Menü **Datei** ein neues Windows-Anwendungsprojekt, indem Sie auf **NewProject**klicken.</span><span class="sxs-lookup"><span data-stu-id="82ff9-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="82ff9-128">Überprüfen Sie im Dialogfeld **Neues Projekt** unter dem Feld **Projekttypen** , ob Windows ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="82ff9-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="82ff9-129">Wählen Sie in der Liste **Vorlagen** die Option **Klassenbibliothek** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="82ff9-130">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82ff9-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="82ff9-131">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="82ff9-132">Der **Projekt-Designer** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82ff9-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="82ff9-133">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="82ff9-134">Aktivieren Sie das Kontrollkästchen **für COM-Interop registrieren** .</span><span class="sxs-lookup"><span data-stu-id="82ff9-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="82ff9-135">So richten Sie den Code in der Klasse ein, um ein COM-Objekt zu erstellen</span><span class="sxs-lookup"><span data-stu-id="82ff9-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="82ff9-136">Doppelklicken Sie in **Projektmappen-Explorer**auf **Class1. vb** , um den Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="82ff9-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="82ff9-137">Benennen Sie die Klasse in `ComClass1` um.</span><span class="sxs-lookup"><span data-stu-id="82ff9-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="82ff9-138">Fügen Sie `ComClass1`die folgenden Konstanten hinzu.</span><span class="sxs-lookup"><span data-stu-id="82ff9-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="82ff9-139">Sie speichern die GUID-Konstanten (Global Unique Identifier), die für die COM-Objekte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="82ff9-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="82ff9-140">Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="82ff9-141">Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="82ff9-142">Klicken Sie auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="82ff9-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="82ff9-143">Ersetzen Sie die leere Zeichenfolge für die `ClassId` durch die GUID, und entfernen Sie die führenden und nachfolgenden geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="82ff9-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="82ff9-144">Wenn beispielsweise die von Guidgen bereitgestellte GUID `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` ist, sollte der Code wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="82ff9-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="82ff9-145">Wiederholen Sie die vorherigen Schritte für die `InterfaceId`-und `EventsId` Konstanten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82ff9-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="82ff9-146">Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. Andernfalls könnte die COM-Komponente mit anderen COM-Komponenten in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="82ff9-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="82ff9-147">Fügen Sie das `ComClass`-Attribut `ComClass1`hinzu, und geben Sie die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID an, wie im folgenden Beispiel gezeigt</span><span class="sxs-lookup"><span data-stu-id="82ff9-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="82ff9-148">COM-Klassen müssen über einen Parameter losen `Public Sub New()` Konstruktor verfügen, oder die Klasse wird nicht ordnungsgemäß registriert.</span><span class="sxs-lookup"><span data-stu-id="82ff9-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="82ff9-149">Fügen Sie der-Klasse einen Parameter losen Konstruktor hinzu:</span><span class="sxs-lookup"><span data-stu-id="82ff9-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="82ff9-150">Fügen Sie der-Klasse Eigenschaften, Methoden und Ereignisse hinzu, und beenden Sie Sie mit einer `End Class`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="82ff9-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="82ff9-151">Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="82ff9-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="82ff9-152">Visual Basic erstellt die Assembly und registriert das COM-Objekt beim Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="82ff9-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="82ff9-153">Die mit Visual Basic generierten COM-Objekte können von anderen Visual Basic Anwendungen nicht verwendet werden, da es sich nicht um echte COM-Objekte handelt.</span><span class="sxs-lookup"><span data-stu-id="82ff9-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="82ff9-154">Versuche, Verweise auf solche COM-Objekte hinzuzufügen, geben einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="82ff9-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="82ff9-155">Weitere Informationen finden Sie unter [com-Interoperabilität in .NET Framework Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="82ff9-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ff9-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82ff9-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="82ff9-157">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="82ff9-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="82ff9-158">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="82ff9-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="82ff9-159">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="82ff9-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="82ff9-160">COM-Interoperabilität in .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="82ff9-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="82ff9-161">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="82ff9-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
