---
title: 'Gewusst wie: Abrufen von Daten in einem bestimmten Datenformat'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 884b017a69e55cfccc9201ad2d101017b0c290b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="517d0-102">Gewusst wie: Abrufen von Daten in einem bestimmten Datenformat</span><span class="sxs-lookup"><span data-stu-id="517d0-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="517d0-103">Die folgenden Beispiele zeigen, wie zum Abrufen von Daten aus einem Datenobjekt in einem angegebenen Format.</span><span class="sxs-lookup"><span data-stu-id="517d0-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="517d0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="517d0-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="517d0-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="517d0-105">Description</span></span>  
 <span data-ttu-id="517d0-106">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> methodenüberladung, um zuerst überprüfen Sie, ob eine angegebene Datenformat ist verfügbar, (systemeigen oder durch automatische Konvertierung), wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> Methode.</span><span class="sxs-lookup"><span data-stu-id="517d0-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="517d0-107">Code</span><span class="sxs-lookup"><span data-stu-id="517d0-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="517d0-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="517d0-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="517d0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="517d0-109">Description</span></span>  
 <span data-ttu-id="517d0-110">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> methodenüberladung, um zuerst überprüfen Sie, ob ein angegebenes Datenformat systemintern verfügbar ist (Auto-Datenformate werden gefiltert); Wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29>Methode.</span><span class="sxs-lookup"><span data-stu-id="517d0-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="517d0-111">Code</span><span class="sxs-lookup"><span data-stu-id="517d0-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="517d0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="517d0-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="517d0-113">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="517d0-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
