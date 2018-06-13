---
title: 'Gewusst wie: Auflisten der Datenformate in einem Datenobjekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: c0e5917d52d9253737a56307beed69bc0255807c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543480"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="e4fde-102">Gewusst wie: Auflisten der Datenformate in einem Datenobjekt</span><span class="sxs-lookup"><span data-stu-id="e4fde-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="e4fde-103">Den folgenden Beispielen wird veranschaulicht, wie die <xref:System.Windows.DataObject.GetFormats%2A> Überladungen der Methode erhalten ein Array von Zeichenfolgen, die jede-Datenformat, die in einem Datenobjekt verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e4fde-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fde-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4fde-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e4fde-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4fde-105">Description</span></span>  
 <span data-ttu-id="e4fde-106">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> methodenüberladung, um ein Array von Zeichenfolgen, die alle verfügbaren Datenformate in ein Datenobjekt (systemeigene und automatisch konvertierbare) abrufen.</span><span class="sxs-lookup"><span data-stu-id="e4fde-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="e4fde-107">Code</span><span class="sxs-lookup"><span data-stu-id="e4fde-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="e4fde-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4fde-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e4fde-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4fde-109">Description</span></span>  
 <span data-ttu-id="e4fde-110">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> Überladung abzurufenden ein Array von Zeichenfolgen, die nur Datenformate in ein Datenobjekt (Auto-Datenformate Formate werden gefiltert) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e4fde-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="e4fde-111">Code</span><span class="sxs-lookup"><span data-stu-id="e4fde-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="e4fde-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4fde-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="e4fde-113">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="e4fde-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
