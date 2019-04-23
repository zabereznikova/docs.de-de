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
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080019"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="bd938-102">Vorgehensweise: Abrufen von Daten in einem bestimmten Datenformat</span><span class="sxs-lookup"><span data-stu-id="bd938-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="bd938-103">Die folgenden Beispiele zeigen, wie Sie Daten von einem Datenobjekt in einem angegebenen Format abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bd938-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd938-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd938-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bd938-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd938-105">Description</span></span>  
 <span data-ttu-id="bd938-106">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> -Überladung verwenden, um zunächst zu überprüfen, ob es sich bei einem angegebenen Datenformat ist verfügbar, (durch systemeigene Funktionen oder durch automatische Konvertierung), wenn das angegebene Format verfügbar ist, im Beispiel ruft ab, die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> Methode.</span><span class="sxs-lookup"><span data-stu-id="bd938-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd938-107">Code</span><span class="sxs-lookup"><span data-stu-id="bd938-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="bd938-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd938-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bd938-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd938-109">Description</span></span>  
 <span data-ttu-id="bd938-110">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> -Überladung verwenden, um zunächst überprüft, ob ein angegebenes Datenformat im System verfügbar ist (Datenformate, die automatisch gefiltert werden); Wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der ab<xref:System.Windows.DataObject.GetData%28System.String%29>Methode.</span><span class="sxs-lookup"><span data-stu-id="bd938-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd938-111">Code</span><span class="sxs-lookup"><span data-stu-id="bd938-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="bd938-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd938-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="bd938-113">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="bd938-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
