---
title: 'Gewusst wie: Erstellen eines Datenobjekts'
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
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 014d5229026a6fdaab203c82932742c7b2c7639e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="999f6-102">Gewusst wie: Erstellen eines Datenobjekts</span><span class="sxs-lookup"><span data-stu-id="999f6-102">How to: Create a Data Object</span></span>
<span data-ttu-id="999f6-103">In den folgenden Beispielen werden verschiedene Möglichkeiten zum Erstellen eines Datenobjekts, das mit den bereitgestellten Konstruktoren der <xref:System.Windows.DataObject> Klasse.</span><span class="sxs-lookup"><span data-stu-id="999f6-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="999f6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="999f6-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="999f6-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-105">Description</span></span>  
 <span data-ttu-id="999f6-106">Im folgenden Codebeispiel wird ein neues Datenobjekt erstellt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) um das Datenobjekt mit einer Zeichenfolge zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="999f6-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="999f6-107">In diesem Fall wird ein entsprechende Datenformat wird automatisch anhand der Typ der gespeicherten Daten bestimmt, und automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="999f6-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-108">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="999f6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-109">Description</span></span>  
 <span data-ttu-id="999f6-110">Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.</span><span class="sxs-lookup"><span data-stu-id="999f6-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-111">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="999f6-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="999f6-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="999f6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-113">Description</span></span>  
 <span data-ttu-id="999f6-114">Im folgenden Codebeispiel wird ein neues Datenobjekt erstellt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) zum Initialisieren des Objekts Daten mit einer Zeichenfolge und einem angegebenen Format.</span><span class="sxs-lookup"><span data-stu-id="999f6-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="999f6-115">In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="999f6-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="999f6-116">Automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="999f6-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-117">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="999f6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-118">Description</span></span>  
 <span data-ttu-id="999f6-119">Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.</span><span class="sxs-lookup"><span data-stu-id="999f6-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-120">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="999f6-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="999f6-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="999f6-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-122">Description</span></span>  
 <span data-ttu-id="999f6-123">Im folgenden Codebeispiel wird ein neues Datenobjekt erstellt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%2A>) zum Initialisieren des Objekts Daten mit einer Zeichenfolge und einem angegebenen Format.</span><span class="sxs-lookup"><span data-stu-id="999f6-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="999f6-124">In diesem Fall wird das Datenformat angegeben, indem eine <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="999f6-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="999f6-125">Automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="999f6-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-126">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="999f6-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-127">Description</span></span>  
 <span data-ttu-id="999f6-128">Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.</span><span class="sxs-lookup"><span data-stu-id="999f6-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-129">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="999f6-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="999f6-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="999f6-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-131">Description</span></span>  
 <span data-ttu-id="999f6-132">Im folgenden Codebeispiel wird ein neues Datenobjekt erstellt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) zum Initialisieren des Objekts Daten mit einer Zeichenfolge und einem angegebenen Format.</span><span class="sxs-lookup"><span data-stu-id="999f6-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="999f6-133">In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="999f6-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="999f6-134">Diese bestimmte Konstruktorüberladung ermöglicht dem Aufrufer angeben, ob die automatische Konvertierung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="999f6-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-135">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="999f6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="999f6-136">Description</span></span>  
 <span data-ttu-id="999f6-137">Der folgende Beispielcode ist eine verkürzte Version des obigen Codes.</span><span class="sxs-lookup"><span data-stu-id="999f6-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="999f6-138">Code</span><span class="sxs-lookup"><span data-stu-id="999f6-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="999f6-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="999f6-139">See Also</span></span>  
 <xref:System.Windows.IDataObject>
