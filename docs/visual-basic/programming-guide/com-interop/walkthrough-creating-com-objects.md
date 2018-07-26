---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: caf0a071d65746f1027052e648ade538d62dc4bb
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245686"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="f0abe-102">Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0abe-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="f0abe-103">Wenn Sie neue Anwendungen oder Komponenten erstellen möchten, empfiehlt es sich zum Erstellen von .NET Framework-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f0abe-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="f0abe-104">Allerdings erleichtert Visual Basic auch .NET Framework-Komponenten für COM verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f0abe-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="f0abe-105">Dadurch können Sie frühere anwendungssuites neue Komponenten bereit, die COM-Komponenten erfordern.</span><span class="sxs-lookup"><span data-stu-id="f0abe-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="f0abe-106">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Visual Basic verwenden, um verfügbar zu machen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Objekte als COM-Objekte mit und ohne COM-Klassenvorlage.</span><span class="sxs-lookup"><span data-stu-id="f0abe-106">This walkthrough demonstrates how to use Visual Basic to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="f0abe-107">Die einfachste Möglichkeit zum COM-Objekte verfügbar zu machen, ist die Verwendung von COM-Klassenvorlage.</span><span class="sxs-lookup"><span data-stu-id="f0abe-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="f0abe-108">COM-Klassenvorlage erstellt eine neue Klasse, und klicken Sie dann Ihr Projekt zum Generieren der Klasse und Interoperabilität-Schicht als COM-Objekt, und registrieren Sie ihn mit dem Betriebssystem konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f0abe-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0abe-109">Obwohl Sie auch eine Klasse, die in Visual Basic erstellt werden, als für nicht verwalteten Code mit COM-Objekt verfügbar machen können, ist nicht "true" COM-Objekt und kann nicht von Visual Basic verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0abe-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="f0abe-110">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f0abe-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="f0abe-111">So erstellen Sie ein COM-Objekt mit der COM-Klassenvorlage</span><span class="sxs-lookup"><span data-stu-id="f0abe-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="f0abe-112">Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** Menü, indem Sie auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="f0abe-113">In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f0abe-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="f0abe-114">Wählen Sie **Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="f0abe-115">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0abe-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="f0abe-116">Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="f0abe-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="f0abe-117">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0abe-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="f0abe-118">Wählen Sie **COM-Klasse** aus der **Vorlagen** aus, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="f0abe-119">Visual Basic fügt eine neue Klasse hinzu, und konfiguriert das neue Projekt für COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="f0abe-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="f0abe-120">Fügen Sie Code wie z. B. Eigenschaften, Methoden und Ereignisse, auf die COM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0abe-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="f0abe-121">Wählen Sie **erstellen ClassLibrary1** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="f0abe-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="f0abe-122">Visual Basic wird die Assembly erstellt und registriert das COM-Objekt mit dem Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="f0abe-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="f0abe-123">Erstellen von COM-Objekten ohne COM-Klassenvorlage</span><span class="sxs-lookup"><span data-stu-id="f0abe-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="f0abe-124">Sie können auch eine COM-Klasse anstelle von COM-Klassenvorlage manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0abe-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="f0abe-125">Dieses Verfahren ist hilfreich, wenn Sie über die Befehlszeile arbeiten oder besser steuern, wie COM-Objekte definiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0abe-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="f0abe-126">Ihr Projekt einrichten, um ein COM-Objekt zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f0abe-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="f0abe-127">Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** Menü, indem Sie auf **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="f0abe-128">In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f0abe-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="f0abe-129">Wählen Sie **Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="f0abe-130">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0abe-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="f0abe-131">In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="f0abe-132">Die **Projekt-Designer** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0abe-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="f0abe-133">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="f0abe-134">Wählen Sie die **für COM-Interop registrieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="f0abe-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="f0abe-135">Der Code in Ihrer Klasse einrichten, um ein COM-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0abe-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="f0abe-136">In **Projektmappen-Explorer**, doppelklicken Sie auf **"Class1.vb"** der Code angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0abe-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="f0abe-137">Benennen Sie die Klasse in `ComClass1` um.</span><span class="sxs-lookup"><span data-stu-id="f0abe-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="f0abe-138">Fügen Sie die folgenden Konstanten zum `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="f0abe-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="f0abe-139">Sie speichert die global eindeutige Bezeichner (GUID)-Konstanten, die die COM-Objekte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f0abe-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  <span data-ttu-id="f0abe-140">Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="f0abe-141">Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="f0abe-142">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="f0abe-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="f0abe-143">Ersetzen Sie die leere Zeichenfolge für die `ClassId` durch die GUID, entfernen Sie die führende und nachgestellte geschweifte Klammern.</span><span class="sxs-lookup"><span data-stu-id="f0abe-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="f0abe-144">Ist z. B. wenn die GUID von Guidgen angegeben `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` und klicken Sie dann der Code wie folgt angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0abe-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  <span data-ttu-id="f0abe-145">Wiederholen Sie die vorherigen Schritte für die `InterfaceId` und `EventsId` Konstanten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0abe-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="f0abe-146">Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. Andernfalls kann die COM-Komponente mit anderen COM_Komponenten in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="f0abe-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="f0abe-147">Hinzufügen der `ComClass` Attribut `ComClass1`, geben Sie die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f0abe-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  <span data-ttu-id="f0abe-148">COM-Klassen müssen eine parameterlose `Public Sub New()` Konstruktor oder die Klasse wird nicht ordnungsgemäß registriert.</span><span class="sxs-lookup"><span data-stu-id="f0abe-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="f0abe-149">Fügen Sie einen parameterlosen Konstruktor der Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="f0abe-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. <span data-ttu-id="f0abe-150">Hinzufügen von Eigenschaften, Methoden und Ereignisse der Klasse, und endet mit einem `End Class` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f0abe-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="f0abe-151">Wählen Sie **Projektmappe** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="f0abe-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="f0abe-152">Visual Basic wird die Assembly erstellt und registriert das COM-Objekt mit dem Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="f0abe-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0abe-153">Die COM-Objekte, die Sie mit Visual Basic generieren können nicht von anderen Visual Basic-Anwendungen verwendet werden, da sie nicht "true" COM-Objekte sind.</span><span class="sxs-lookup"><span data-stu-id="f0abe-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="f0abe-154">Versucht, Verweise auf diese COM-Objekte hinzufügen, werden ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f0abe-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="f0abe-155">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f0abe-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0abe-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0abe-156">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [<span data-ttu-id="f0abe-157">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="f0abe-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="f0abe-158">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="f0abe-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="f0abe-159">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0abe-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="f0abe-160">COM-Interoperabilität in .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f0abe-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="f0abe-161">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="f0abe-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
