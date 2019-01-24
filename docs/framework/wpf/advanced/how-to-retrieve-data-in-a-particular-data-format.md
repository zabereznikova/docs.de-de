---
title: 'Vorgehensweise: Abrufen von Daten in einem bestimmten Datenformat'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: d11374cbc70210e648e93a385c4a9fbca112c09f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718294"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="7b3fa-102">Vorgehensweise: Abrufen von Daten in einem bestimmten Datenformat</span><span class="sxs-lookup"><span data-stu-id="7b3fa-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="7b3fa-103">Die folgenden Beispiele zeigen, wie Sie Daten von einem Datenobjekt in einem angegebenen Format abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7b3fa-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b3fa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b3fa-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7b3fa-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b3fa-105">Description</span></span>  
 <span data-ttu-id="7b3fa-106">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> -Überladung verwenden, um zunächst zu überprüfen, ob es sich bei einem angegebenen Datenformat ist verfügbar, (durch systemeigene Funktionen oder durch automatische Konvertierung), wenn das angegebene Format verfügbar ist, im Beispiel ruft ab, die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> Methode.</span><span class="sxs-lookup"><span data-stu-id="7b3fa-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7b3fa-107">Code</span><span class="sxs-lookup"><span data-stu-id="7b3fa-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="7b3fa-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b3fa-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7b3fa-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b3fa-109">Description</span></span>  
 <span data-ttu-id="7b3fa-110">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> -Überladung verwenden, um zunächst überprüft, ob ein angegebenes Datenformat im System verfügbar ist (Datenformate, die automatisch gefiltert werden); Wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der ab<xref:System.Windows.DataObject.GetData%28System.String%29>Methode.</span><span class="sxs-lookup"><span data-stu-id="7b3fa-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7b3fa-111">Code</span><span class="sxs-lookup"><span data-stu-id="7b3fa-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="7b3fa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b3fa-112">See also</span></span>
- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="7b3fa-113">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="7b3fa-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
