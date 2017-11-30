---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff7d3868a2e3ddaba06ebc6f98c8eacfc7299366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="5b424-102">Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b424-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="5b424-103">Für die Erstellung neuer Anwendungen oder Komponenten, empfiehlt es sich um .NET Framework-Assemblys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b424-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="5b424-104">Allerdings [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erleichtert es .NET Framework-Komponenten für COM verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="5b424-104">However, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="5b424-105">Dadurch können Sie neue Komponenten für frühere Anwendung Sammlungen bereitstellen, die COM-Komponenten erfordern.</span><span class="sxs-lookup"><span data-stu-id="5b424-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="5b424-106">Diese exemplarische Vorgehensweise veranschaulicht, wie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verfügbar machen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Objekte als COM-Objekte, die mit und ohne die COM-Klassenvorlage.</span><span class="sxs-lookup"><span data-stu-id="5b424-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="5b424-107">Die einfachste Möglichkeit zum Verfügbarmachen von COM-Objekten wird mithilfe der Vorlage der COM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5b424-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="5b424-108">Die COM-Klassenvorlage wird eine neue Klasse erstellt und konfiguriert anschließend das Projekt, um die Klasse und Interoperabilität Ebene als COM-Objekt zu generieren, und registrieren Sie ihn mit dem Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="5b424-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b424-109">Obwohl Sie auch eine Klasse erstellt, die verfügbar machen können [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] als COM-Objekt für nicht verwalteten Code verwenden, ist kein "true" COM-Objekt und kann nicht verwendet werden, indem [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b424-109">Although you can also expose a class created in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="5b424-110">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="5b424-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="5b424-111">So erstellen ein COM-Objekt mithilfe der Vorlage der COM-Klasse</span><span class="sxs-lookup"><span data-stu-id="5b424-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="5b424-112">Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="5b424-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="5b424-113">In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5b424-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="5b424-114">Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b424-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="5b424-115">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b424-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="5b424-116">Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="5b424-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="5b424-117">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b424-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="5b424-118">Wählen Sie **COM-Klasse** aus der **Vorlagen** aus, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5b424-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5b424-119">Fügt eine neue Klasse hinzu, und das neue Projekt für COM-Interop konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5b424-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="5b424-120">Fügen Sie Code, z. B. Eigenschaften, Methoden und Ereignisse, auf die COM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5b424-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="5b424-121">Wählen Sie **erstellen "ClassLibrary1"** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="5b424-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5b424-122">erstellt die Assembly und das COM-Objekt mit dem Betriebssystem registriert.</span><span class="sxs-lookup"><span data-stu-id="5b424-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="5b424-123">Erstellen von COM-Objekte, ohne die Vorlage für die COM-Klasse</span><span class="sxs-lookup"><span data-stu-id="5b424-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="5b424-124">Sie können auch eine COM-Klasse anstelle der COM-Klassenvorlage manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b424-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="5b424-125">Dieses Verfahren ist hilfreich, bei der Arbeit von der Befehlszeile aus, oder wenn Sie besser steuern, wie COM-Objekte definiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b424-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="5b424-126">Einrichten Ihres Projekts festlegen, um ein COM-Objekt zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5b424-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="5b424-127">Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="5b424-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="5b424-128">In der **neues Projekt** im Dialogfeld unter die **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5b424-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="5b424-129">Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b424-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="5b424-130">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b424-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="5b424-131">In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5b424-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="5b424-132">Die **Projekt-Designer** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b424-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="5b424-133">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="5b424-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="5b424-134">Wählen Sie die **für COM-Interop registrieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="5b424-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="5b424-135">Richten Sie den Code in Ihrer Klasse zum Erstellen eines COM-Objekts</span><span class="sxs-lookup"><span data-stu-id="5b424-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="5b424-136">In **Projektmappen-Explorer**, doppelklicken Sie auf **Class1.vb** um ihren Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5b424-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="5b424-137">Benennen Sie die Klasse in `ComClass1` um.</span><span class="sxs-lookup"><span data-stu-id="5b424-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="5b424-138">Fügen Sie die folgenden Konstanten `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="5b424-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="5b424-139">Sie werden die Konstanten der global eindeutige Bezeichner (GUID) gespeichert, die die COM-Objekte aufweisen müssen.</span><span class="sxs-lookup"><span data-stu-id="5b424-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  <span data-ttu-id="5b424-140">Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5b424-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="5b424-141">Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="5b424-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="5b424-142">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="5b424-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="5b424-143">Ersetzen Sie die leere Zeichenfolge für die `ClassId` mit der GUID entfernen Sie die führende und nachgestellte geschweifte Klammern.</span><span class="sxs-lookup"><span data-stu-id="5b424-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="5b424-144">Ist beispielsweise, wenn die GUID von Guidgen bereitgestellte `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` und klicken Sie dann der Code wie folgt angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b424-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  <span data-ttu-id="5b424-145">Wiederholen Sie die vorherigen Schritte für die `InterfaceId` und `EventsId` Konstanten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b424-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="5b424-146">Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. andernfalls, COM-Komponente einen Konflikt mit anderen COM-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="5b424-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="5b424-147">Hinzufügen der `ComClass` -Attribut `ComClass1`, die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5b424-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  <span data-ttu-id="5b424-148">COM-Klassen müssen eine parameterlose `Public Sub New()` Konstruktor oder die Klasse wird nicht ordnungsgemäß registriert.</span><span class="sxs-lookup"><span data-stu-id="5b424-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="5b424-149">Fügen Sie der Klasse einen parameterlosen Konstruktor hinzu:</span><span class="sxs-lookup"><span data-stu-id="5b424-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. <span data-ttu-id="5b424-150">Hinzufügen von Eigenschaften, Methoden und Ereignisse auf die Klasse, beenden ihn mit einer `End Class` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5b424-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="5b424-151">Wählen Sie **Projektmappe** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="5b424-151">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5b424-152">erstellt die Assembly und das COM-Objekt mit dem Betriebssystem registriert.</span><span class="sxs-lookup"><span data-stu-id="5b424-152"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b424-153">Die COM-Objekte, die Sie generieren mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kann nicht verwendet werden, von anderen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Anwendungen, da sie nicht auf "true" COM-Objekte sind.</span><span class="sxs-lookup"><span data-stu-id="5b424-153">The COM objects you generate with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot be used by other [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="5b424-154">Versuche, Verweise auf diese COM-Objekte hinzuzufügen, werden ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5b424-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="5b424-155">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework-Anwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="5b424-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b424-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b424-156">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [<span data-ttu-id="5b424-157">COM-Interop</span><span class="sxs-lookup"><span data-stu-id="5b424-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="5b424-158">Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten</span><span class="sxs-lookup"><span data-stu-id="5b424-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="5b424-159">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5b424-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="5b424-160">COM-Interoperabilität in .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5b424-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="5b424-161">Problembehandlung bei der Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="5b424-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
