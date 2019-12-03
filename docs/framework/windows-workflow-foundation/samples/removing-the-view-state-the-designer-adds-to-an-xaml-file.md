---
title: 'Entfernen des Ansichts Zustands, der vom Designer zu einer XAML-Datei hinzugefügt wird: WF'
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: f431275140e821aa5ec4d2235322f06be87d5ee2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715611"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="1b201-102">Entfernen des Ansichts Zustands, der vom Designer zu einer XAML-Datei hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="1b201-102">Removing the view state the designer adds to an XAML file</span></span>

<span data-ttu-id="1b201-103">Dieses Beispiel veranschaulicht, wie eine Klasse erstellt wird, die von <xref:System.Xaml.XamlWriter> abgeleitet wird, und entfernt den Ansichtszustand aus einer XAML-Datei.</span><span class="sxs-lookup"><span data-stu-id="1b201-103">This sample demonstrates how to create a class that derives from <xref:System.Xaml.XamlWriter> and removes view state from a XAML file.</span></span> <span data-ttu-id="1b201-104">Windows Workflow-Designer schreibt Informationen in das XAML-Dokument, das als Ansichts Zustand bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="1b201-104">Windows Workflow Designer writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="1b201-105">Der Ansichtszustand bezieht sich auf die Informationen, die während der Entwurfszeit erforderlich sind, z. B. die Layoutpositionierung, jedoch nicht zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="1b201-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> <span data-ttu-id="1b201-106">Workflow-Designer fügt diese Informationen in das XAML-Dokument ein, während es bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="1b201-106">Workflow Designer inserts this information into the XAML document as it is edited.</span></span> <span data-ttu-id="1b201-107">Workflow-Designer schreibt den Ansichts Zustand in die XAML-Datei mit dem Attribut `mc:Ignorable`, sodass diese Informationen nicht geladen werden, wenn die Laufzeit die XAML-Datei lädt.</span><span class="sxs-lookup"><span data-stu-id="1b201-107">Workflow Designer writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="1b201-108">In diesem Beispiel wird veranschaulicht, wie eine Klasse erstellt wird, mit der diese Ansichtszustandsinformationen bei der Verarbeitung von XAML-Knoten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1b201-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="1b201-109">Diskussion</span><span class="sxs-lookup"><span data-stu-id="1b201-109">Discussion</span></span>

<span data-ttu-id="1b201-110">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Writer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1b201-110">This sample demonstrates how to create a custom writer.</span></span>

<span data-ttu-id="1b201-111">Zum Erstellen eines benutzerdefinierten XAML-Writers müssen Sie eine Klasse erstellen, die von <xref:System.Xaml.XamlWriter> erbt.</span><span class="sxs-lookup"><span data-stu-id="1b201-111">To build a custom XAML writer, create a class that inherits from <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="1b201-112">Da XAML-Writer oft geschachtelt sind, ist es üblich, einen "inneren" XAML-Writer nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="1b201-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="1b201-113">Diese "inneren" Writer können als Verweis auf den verbleibenden Stapel von XAML-Writern angesehen werden, sodass mehrere Einstiegspunkte funktionieren und die Verarbeitung dann an den Rest des Stapels delegiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b201-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

<span data-ttu-id="1b201-114">In diesem Beispiel gibt es einige relevante Elemente.</span><span class="sxs-lookup"><span data-stu-id="1b201-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="1b201-115">Eines ist die Überprüfung, ob das geschriebene Element aus einem Designernamespace stammt.</span><span class="sxs-lookup"><span data-stu-id="1b201-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="1b201-116">Beachten Sie, dass dies die Verwendung anderer Typen des Designernamespace in einem Workflow nicht mehr ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1b201-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

<span data-ttu-id="1b201-117">Hierdurch wird auch ein Stapel von XAML-Membern erstellt, die beim Durchlaufen des Knotenstreams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b201-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="1b201-118">Die verbleibende Arbeit dieses Beispiels ist zum größten Teil in der `WriteStartMember`-Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b201-118">The remaining work of this sample is largely contained in the `WriteStartMember` method.</span></span>

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

<span data-ttu-id="1b201-119">Nachfolgende Methoden können überprüfen, ob sie immer noch in einem Ansichtszustandscontainer enthalten sind. Wenn dies der Fall ist, können sie zurückkehren und den Knoten nicht im Writerstapel weiter übergeben.</span><span class="sxs-lookup"><span data-stu-id="1b201-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

<span data-ttu-id="1b201-120">Um einen benutzerdefinierten XAML-Writer verwenden zu können, müssen Sie ihn in einem Stapel XAML-Writer verketten.</span><span class="sxs-lookup"><span data-stu-id="1b201-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="1b201-121">Der folgende Code zeigt diese Verwendung.</span><span class="sxs-lookup"><span data-stu-id="1b201-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a><span data-ttu-id="1b201-122">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b201-122">To use this sample</span></span>

1. <span data-ttu-id="1b201-123">Öffnen Sie mit Visual Studio 2010 die Projektmappendatei "viewstatuecleaningwriter. sln".</span><span class="sxs-lookup"><span data-stu-id="1b201-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="1b201-124">Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zu dem Verzeichnis, in dem ViewStageCleaningWriter.exe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1b201-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="1b201-125">Führen Sie ViewStateCleaningWriter.exe für die Datei Workflow1.xaml aus.</span><span class="sxs-lookup"><span data-stu-id="1b201-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="1b201-126">Die Syntax für die ausführbare Datei ist im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1b201-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="1b201-127">Dadurch wird eine XAML-Datei an \[Ausgabedatei] ausgegeben, die alle Ansichts Zustandsinformationen entfernt hat.</span><span class="sxs-lookup"><span data-stu-id="1b201-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="1b201-128">Für einen <xref:System.Activities.Statements.Sequence>-Workflow wird eine Reihe von Virtualisierungshinweisen entfernt.</span><span class="sxs-lookup"><span data-stu-id="1b201-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="1b201-129">Dies veranlasst den Designer, das Layout beim nächsten Laden neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="1b201-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="1b201-130">Wenn Sie dieses Beispiel für ein <xref:System.Activities.Statements.Flowchart> verwenden, werden alle Positionierungs- und Zeilenroutinginformationen entfernt. Bei nachfolgendem Laden in den Designer werden alle Aktivitäten auf der linken Seite des Bildschirms gestapelt.</span><span class="sxs-lookup"><span data-stu-id="1b201-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="1b201-131">So erstellen Sie eine Beispiel-XAML-Datei zur Verwendung mit diesem Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b201-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="1b201-132">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="1b201-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="1b201-133">So erstellen Sie eine neue Workflowkonsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="1b201-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="1b201-134">Legen Sie einige Aktivitäten in der Entwurfsfläche ab.</span><span class="sxs-lookup"><span data-stu-id="1b201-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="1b201-135">Speichern Sie die Workflow-XAML-Datei.</span><span class="sxs-lookup"><span data-stu-id="1b201-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="1b201-136">Überprüfen Sie die XAML-Datei auf die Eigenschaften, die dem Ansichtszustand zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1b201-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b201-137">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1b201-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1b201-138">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1b201-138">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="1b201-139">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1b201-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1b201-140">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1b201-140">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
