---
title: "Gewusst wie: Hinzufügen von Daten zur Zwischenablage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47858af6d4e3dc5f29632c5a74f2431a2cc200b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="98efa-102">Gewusst wie: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98efa-102">How to: Add Data to the Clipboard</span></span>
<span data-ttu-id="98efa-103">Die <xref:System.Windows.Forms.Clipboard> Klasse enthält Methoden, die Sie für die Interaktion mit der Zwischenablage-Feature des Windows-Betriebssystems verwenden können.</span><span class="sxs-lookup"><span data-stu-id="98efa-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="98efa-104">Viele Anwendungen verwenden die Zwischenablage als temporäre Repository für Daten.</span><span class="sxs-lookup"><span data-stu-id="98efa-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="98efa-105">Beispielsweise verwenden Textverarbeitungsprogramme Zwischenablage während Ausschneide- und Einfügevorgänge.</span><span class="sxs-lookup"><span data-stu-id="98efa-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="98efa-106">Die Zwischenablage eignet sich auch zum Übertragen von Daten aus einer Anwendung in eine andere.</span><span class="sxs-lookup"><span data-stu-id="98efa-106">The Clipboard is also useful for transferring data from one application to another.</span></span>  
  
 <span data-ttu-id="98efa-107">Wenn Sie Daten in die Zwischenablage hinzufügen, können Sie das Datenformat, die angeben, damit andere Anwendungen die Daten erkennen können, ob dieses Format verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="98efa-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="98efa-108">Sie können auch Daten hinzufügen, in die Zwischenablage in mehreren verschiedenen Formaten, um die Anzahl der anderen Anwendungen zu erhöhen, die möglicherweise die Daten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="98efa-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>  
  
 <span data-ttu-id="98efa-109">Ein Zwischenablageformat ist eine Zeichenfolge, die das Format identifiziert, damit eine Anwendung, die dieses Format wird verwendet, die zugehörigen Daten abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="98efa-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="98efa-110">Die <xref:System.Windows.Forms.DataFormats> Klasse bietet vordefinierte Formatnamen für Ihre Verwendung.</span><span class="sxs-lookup"><span data-stu-id="98efa-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="98efa-111">Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format.</span><span class="sxs-lookup"><span data-stu-id="98efa-111">You can also use your own format names or use the type of an object as its format.</span></span>  
  
 <span data-ttu-id="98efa-112">Verwenden Sie zum Hinzufügen von Daten in einem oder mehreren Formaten in die Zwischenablage die <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="98efa-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="98efa-113">Sie können jedes Objekt an diese Methode übergeben, aber um Daten in mehreren Formaten hinzuzufügen, müssen Sie zuerst die Daten hinzufügen, auf ein separates Objekt dienen zum Arbeiten mit mehreren Formaten.</span><span class="sxs-lookup"><span data-stu-id="98efa-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="98efa-114">In der Regel werden Sie Daten aus die Hinzufügen einer <xref:System.Windows.Forms.DataObject>, aber Sie können einen beliebigen Typ, der implementiert die <xref:System.Windows.Forms.IDataObject> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="98efa-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>  
  
 <span data-ttu-id="98efa-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], Sie können Daten direkt in die Zwischenablage hinzufügen, mit der neue Methoden, um grundlegende Aufgaben der Zwischenablage zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="98efa-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="98efa-116">Verwenden Sie diese Methoden, bei der Arbeit mit Daten in einem einzelnen, gemeinsamen Format, z. B. Text.</span><span class="sxs-lookup"><span data-stu-id="98efa-116">Use these methods when you work with data in a single, common format such as text.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98efa-117">Alle Windows-basierten Anwendungen Freigabe die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="98efa-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="98efa-118">Aus diesem Grund werden die Inhalte können geändert werden, beim Wechsel zu einer anderen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="98efa-118">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="98efa-119">Die <xref:System.Windows.Forms.Clipboard> Klasse kann nur verwendet werden, in Threads auf Singlethread-Apartment (STA) Modus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="98efa-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="98efa-120">Zum Verwenden dieser Klasse sicher, dass Ihre `Main` Methode markiert ist, mit der <xref:System.STAThreadAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="98efa-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
>   
>  <span data-ttu-id="98efa-121">Ein Objekt muss für ihn in die Zwischenablage zu versetzen serialisierbar sein.</span><span class="sxs-lookup"><span data-stu-id="98efa-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="98efa-122">Um einen Typ serialisierbar zu machen, kennzeichnen Sie ihn mit der <xref:System.SerializableAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="98efa-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="98efa-123">Wenn Sie ein nicht serialisierbares Objekt an eine Zwischenablage-Methode übergeben, wird die Methode fehl, ohne eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="98efa-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="98efa-124">Weitere Informationen zur Serialisierung finden Sie unter <xref:System.Runtime.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="98efa-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="98efa-125">Zum Hinzufügen von Daten in einem einzelnen, gemeinsamen-Format in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98efa-125">To add data to the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="98efa-126">Verwenden der <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, oder <xref:System.Windows.Forms.Clipboard.SetText%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="98efa-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="98efa-127">Diese Methoden stehen nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98efa-127">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="98efa-128">Zum Hinzufügen von Daten in einem benutzerdefinierten Format in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98efa-128">To add data to the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="98efa-129">Verwenden der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode mit einem benutzerdefinierten Formatnamen.</span><span class="sxs-lookup"><span data-stu-id="98efa-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="98efa-130">Diese Methode ist nur in verfügbar [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98efa-130">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="98efa-131">Sie können auch die vordefinierten Formatnamen mit der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="98efa-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="98efa-132">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.</span><span class="sxs-lookup"><span data-stu-id="98efa-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="98efa-133">Zum Hinzufügen von Daten in mehreren Formaten in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98efa-133">To add data to the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="98efa-134">Verwenden der <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> Methode und übergeben einer <xref:System.Windows.Forms.DataObject> , die Ihre Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="98efa-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="98efa-135">Verwenden Sie diese Methode zum Hinzufügen von Daten in die Zwischenablage in Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98efa-135">You must use this method to add data to the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="98efa-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98efa-136">See Also</span></span>  
 [<span data-ttu-id="98efa-137">Drag & Drop-Vorgänge und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98efa-137">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [<span data-ttu-id="98efa-138">Gewusst wie: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98efa-138">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
