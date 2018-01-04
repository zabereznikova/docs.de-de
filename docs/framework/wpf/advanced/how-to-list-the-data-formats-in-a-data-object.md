---
title: 'Gewusst wie: Auflisten der Datenformate in einem Datenobjekt'
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
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb27928031b551da2957aab0696646e8adc3f803
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="dc9d8-102">Gewusst wie: Auflisten der Datenformate in einem Datenobjekt</span><span class="sxs-lookup"><span data-stu-id="dc9d8-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="dc9d8-103">Den folgenden Beispielen wird veranschaulicht, wie die <xref:System.Windows.DataObject.GetFormats%2A> Überladungen der Methode erhalten ein Array von Zeichenfolgen, die jede-Datenformat, die in einem Datenobjekt verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dc9d8-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc9d8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc9d8-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="dc9d8-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc9d8-105">Description</span></span>  
 <span data-ttu-id="dc9d8-106">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> methodenüberladung, um ein Array von Zeichenfolgen, die alle verfügbaren Datenformate in ein Datenobjekt (systemeigene und automatisch konvertierbare) abrufen.</span><span class="sxs-lookup"><span data-stu-id="dc9d8-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="dc9d8-107">Code</span><span class="sxs-lookup"><span data-stu-id="dc9d8-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="dc9d8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc9d8-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="dc9d8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc9d8-109">Description</span></span>  
 <span data-ttu-id="dc9d8-110">Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> Überladung abzurufenden ein Array von Zeichenfolgen, die nur Datenformate in ein Datenobjekt (Auto-Datenformate Formate werden gefiltert) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc9d8-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="dc9d8-111">Code</span><span class="sxs-lookup"><span data-stu-id="dc9d8-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="dc9d8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc9d8-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="dc9d8-113">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="dc9d8-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
