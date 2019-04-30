---
title: 'Vorgehensweise: Auflisten der Datenformate in einem Datenobjekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001493"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="a1b93-102">Vorgehensweise: Auflisten der Datenformate in einem Datenobjekt</span><span class="sxs-lookup"><span data-stu-id="a1b93-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="a1b93-103">Die folgenden Beispiele zeigen, wie Sie mit der <xref:System.Windows.DataObject.GetFormats%2A> Überladungen der Methode erhalten ein Array von Zeichenfolgen, die jede Datenformat, das in einem Datenobjekt verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a1b93-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1b93-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1b93-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a1b93-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1b93-105">Description</span></span>  
 <span data-ttu-id="a1b93-106">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> -Überladung verwenden, um ein Array von Zeichenfolgen, die alle verfügbaren Datenformate in einem Datenobjekt (systemeigene und automatisch konvertierbare) abrufen.</span><span class="sxs-lookup"><span data-stu-id="a1b93-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="a1b93-107">Code</span><span class="sxs-lookup"><span data-stu-id="a1b93-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="a1b93-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1b93-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a1b93-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1b93-109">Description</span></span>  
 <span data-ttu-id="a1b93-110">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> -Überladung verwenden, um ein Array von Zeichenfolgen, die nur verfügbaren Datenformate in einem Datenobjekt (automatisch konvertierbare Daten Formate gefiltert werden) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a1b93-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="a1b93-111">Code</span><span class="sxs-lookup"><span data-stu-id="a1b93-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="a1b93-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1b93-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="a1b93-113">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="a1b93-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
