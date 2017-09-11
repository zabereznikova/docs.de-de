---
title: 'Exemplarische Vorgehensweise: Erstellen von COM-Objekten mit Visual Basic | Microsoft-Dokumentation'
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
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
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
ms.openlocfilehash: 859a8fc7440eecc0cadbfa8ea236dad7cae99247
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="cb805-102">Exemplarische Vorgehensweise: Erstellen von COM-Objekten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb805-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="cb805-103">Beim Erstellen neuer Anwendungen oder Komponenten ist es besser, .NET Framework-Assemblys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb805-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="cb805-104">Allerdings [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erleichtert auch .NET Framework-Komponenten für COM verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="cb805-104">However, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="cb805-105">Dadurch können Sie neue Komponenten für frühere anwendungssuites bereitstellen, die COM-Komponenten erfordern.</span><span class="sxs-lookup"><span data-stu-id="cb805-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="cb805-106">Diese exemplarische Vorgehensweise veranschaulicht, wie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verfügbar machen [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Objekte als COM-Objekte, die sowohl mit als auch ohne COM-Klassenvorlage.</span><span class="sxs-lookup"><span data-stu-id="cb805-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to expose [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="cb805-107">Die einfachste Möglichkeit, die COM-Objekte verfügbar machen, wird mithilfe der COM-Klassenvorlage.</span><span class="sxs-lookup"><span data-stu-id="cb805-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="cb805-108">COM-Klassenvorlage erstellt eine neue Klasse und konfiguriert anschließend das Projekt, um die Klasse und Interoperabilität Ebene als COM-Objekt zu generieren und mit dem Betriebssystem zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="cb805-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb805-109">Obwohl Sie auch eine Klasse erstellt, die zur Verfügung stellen können [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] als COM-Objekt für nicht verwalteten Code verwenden, ist es sich nicht um ein echtes COM-Objekt und kann nicht verwendet werden, indem [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb805-109">Although you can also expose a class created in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="cb805-110">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="cb805-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="cb805-111">So erstellen Sie ein COM-Objekt mit der COM-Klassenvorlage</span><span class="sxs-lookup"><span data-stu-id="cb805-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="cb805-112">Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="cb805-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="cb805-113">In der **neues Projekt** im Dialogfeld unter den **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb805-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="cb805-114">Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb805-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="cb805-115">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb805-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="cb805-116">Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="cb805-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="cb805-117">Die **neues Element hinzufügen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb805-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="cb805-118">Wählen Sie **COM-Klasse** aus der **Vorlagen** aus, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cb805-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="cb805-119">Fügt eine neue Klasse hinzu und konfiguriert das neue Projekt für COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="cb805-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="cb805-120">Fügen Sie Code wie z. B. Eigenschaften, Methoden und Ereignisse, die COM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cb805-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="cb805-121">Wählen Sie **ClassLibrary1 erstellen** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="cb805-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="cb805-122">erstellt die Assembly und registriert das COM-Objekt mit dem Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="cb805-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="cb805-123">Erstellen von COM-Objekten ohne die COM-Klassenvorlage</span><span class="sxs-lookup"><span data-stu-id="cb805-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="cb805-124">Sie können auch eine COM-Klasse statt der COM-Klassenvorlage manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb805-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="cb805-125">Dieses Verfahren ist hilfreich, wenn Sie über die Befehlszeile arbeiten, oder wenn Sie möchten, dass mehr Kontrolle über die Definition von COM-Objekten.</span><span class="sxs-lookup"><span data-stu-id="cb805-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="cb805-126">Um Ihr Projekt einzurichten, um ein COM-Objekt zu generieren.</span><span class="sxs-lookup"><span data-stu-id="cb805-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="cb805-127">Öffnen Sie ein neues Windows-Anwendungsprojekt aus der **Datei** durch Klicken auf **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="cb805-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="cb805-128">In der **neues Projekt** im Dialogfeld unter den **Projekttypen** Feld, überprüfen Sie, dass Windows aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb805-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="cb805-129">Wählen Sie **-Klassenbibliothek** aus der **Vorlagen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb805-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="cb805-130">Das neue Projekt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb805-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="cb805-131">In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cb805-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="cb805-132">Die **Projekt-Designer** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb805-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="cb805-133">Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="cb805-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="cb805-134">Wählen Sie die **für COM-Interop registrieren** das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="cb805-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="cb805-135">Der Code in der Klasse einrichten, um ein COM-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb805-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="cb805-136">In **Projektmappen-Explorer**, doppelklicken Sie auf **Class1.vb** um den Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cb805-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="cb805-137">Benennen Sie die Klasse in `ComClass1` um.</span><span class="sxs-lookup"><span data-stu-id="cb805-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="cb805-138">Fügen Sie die folgenden Konstanten `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="cb805-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="cb805-139">Sie speichert die Konstanten der global eindeutige Bezeichner (GUID), die die COM-Objekte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cb805-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     <span data-ttu-id="cb805-140">[!code-vb[VbVbalrInterop&#2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb805-140">[!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span></span>  
  
4.  <span data-ttu-id="cb805-141">Auf der **Tools** Menü klicken Sie auf **Guid erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cb805-141">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="cb805-142">In der **GUID erstellen** im Dialogfeld klicken Sie auf **Registrierungsformat** , und klicken Sie dann auf **Kopie**.</span><span class="sxs-lookup"><span data-stu-id="cb805-142">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="cb805-143">Klicken Sie auf **beenden**.</span><span class="sxs-lookup"><span data-stu-id="cb805-143">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="cb805-144">Ersetzen Sie die leere Zeichenfolge für die `ClassId` durch die GUID, entfernen Sie die führende und nachfolgende geschweifte Klammern.</span><span class="sxs-lookup"><span data-stu-id="cb805-144">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="cb805-145">Ist z. B. wenn die GUID von Guidgen bereitgestellte `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` und dann der Code wie folgt angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb805-145">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     <span data-ttu-id="cb805-146">[!code-vb[VbVbalrInterop&3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb805-146">[!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span></span>  
  
6.  <span data-ttu-id="cb805-147">Wiederholen Sie die vorherigen Schritte für die `InterfaceId` und `EventsId` Konstanten, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cb805-147">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     <span data-ttu-id="cb805-148">[!code-vb[VbVbalrInterop&4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb805-148">[!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb805-149">Stellen Sie sicher, dass die GUIDs neu und eindeutig sind. Andernfalls kann die COM-Komponente mit anderen COM_Komponenten einen Konflikt.</span><span class="sxs-lookup"><span data-stu-id="cb805-149">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="cb805-150">Hinzufügen der `ComClass` -Attribut `ComClass1`, geben Sie die GUIDs für die Klassen-ID, die Schnittstellen-ID und die Ereignis-ID wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb805-150">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     <span data-ttu-id="cb805-151">[!code-vb[VbVbalrInterop&5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb805-151">[!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span></span>  
  
8.  <span data-ttu-id="cb805-152">COM-Klassen müssen eine parameterlose `Public Sub New()` Konstruktor oder die Klasse wird nicht ordnungsgemäß registriert.</span><span class="sxs-lookup"><span data-stu-id="cb805-152">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="cb805-153">Fügen Sie der Klasse einen parameterlosen Konstruktor hinzu:</span><span class="sxs-lookup"><span data-stu-id="cb805-153">Add a parameterless constructor to the class:</span></span>  
  
     <span data-ttu-id="cb805-154">[!code-vb[VbVbalrInterop&6;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb805-154">[!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span></span>  
  
9. <span data-ttu-id="cb805-155">Hinzufügen von Eigenschaften, Methoden und Ereignisse auf die Klasse, und endet mit einem `End Class` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="cb805-155">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="cb805-156">Wählen Sie **Projektmappe** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="cb805-156">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="cb805-157">erstellt die Assembly und registriert das COM-Objekt mit dem Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="cb805-157"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb805-158">Die COM-Objekte, die Sie generieren mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kann nicht verwendet werden, von anderen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Applications, da sie nicht auf "true" COM-Objekte sind.</span><span class="sxs-lookup"><span data-stu-id="cb805-158">The COM objects you generate with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot be used by other [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="cb805-159">Versucht, Verweise auf solche COM-Objekte hinzuzufügen, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="cb805-159">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="cb805-160">Weitere Informationen finden Sie unter [COM-Interoperabilität in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="cb805-160">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb805-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb805-161">See Also</span></span>  
 <span data-ttu-id="cb805-162"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="cb805-162"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>   
<span data-ttu-id="cb805-163"> [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="cb805-163"> [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="cb805-164"> [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="cb805-164"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="cb805-165"> [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="cb805-165"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="cb805-166"> [COM-Interoperabilität in .NET Framework-Clientanwendungen](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cb805-166"> [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="cb805-167"> [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="cb805-167"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span></span>
