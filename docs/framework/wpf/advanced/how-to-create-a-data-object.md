---
title: 'Vorgehensweise: Erstellen eines Datenobjekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: f7bdfbf3dba0c700513348195c1d031d4c2c8b65
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370591"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="0342d-102">Vorgehensweise: Erstellen eines Datenobjekts</span><span class="sxs-lookup"><span data-stu-id="0342d-102">How to: Create a Data Object</span></span>
<span data-ttu-id="0342d-103">Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen eines Datenobjekts, das mit den Konstruktoren, die von bereitgestellte der <xref:System.Windows.DataObject> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0342d-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0342d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0342d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0342d-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-105">Description</span></span>  
 <span data-ttu-id="0342d-106">Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0342d-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="0342d-107">In diesem Fall wird ein geeignetes Datenformat automatisch anhand der Typ der gespeicherten Daten bestimmt, und der gespeicherten Daten der automatischen Umstellung ist standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="0342d-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-108">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="0342d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-109">Description</span></span>  
 <span data-ttu-id="0342d-110">Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.</span><span class="sxs-lookup"><span data-stu-id="0342d-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-111">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="0342d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0342d-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0342d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-113">Description</span></span>  
 <span data-ttu-id="0342d-114">Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.</span><span class="sxs-lookup"><span data-stu-id="0342d-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="0342d-115">In diesem Fall wird das Format der Daten durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="0342d-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="0342d-116">Automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="0342d-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-117">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="0342d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-118">Description</span></span>  
 <span data-ttu-id="0342d-119">Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.</span><span class="sxs-lookup"><span data-stu-id="0342d-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-120">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="0342d-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0342d-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0342d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-122">Description</span></span>  
 <span data-ttu-id="0342d-123">Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%2A>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.</span><span class="sxs-lookup"><span data-stu-id="0342d-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="0342d-124">In diesem Fall wird das Format der Daten angegeben, indem eine <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="0342d-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="0342d-125">Automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.</span><span class="sxs-lookup"><span data-stu-id="0342d-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-126">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="0342d-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-127">Description</span></span>  
 <span data-ttu-id="0342d-128">Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.</span><span class="sxs-lookup"><span data-stu-id="0342d-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-129">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="0342d-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0342d-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0342d-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-131">Description</span></span>  
 <span data-ttu-id="0342d-132">Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.</span><span class="sxs-lookup"><span data-stu-id="0342d-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="0342d-133">In diesem Fall wird das Format der Daten durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="0342d-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="0342d-134">Diese bestimmte Konstruktorüberladung ermöglicht dem Aufrufer angeben, ob die automatische Konvertierung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="0342d-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-135">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="0342d-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0342d-136">Description</span></span>  
 <span data-ttu-id="0342d-137">Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.</span><span class="sxs-lookup"><span data-stu-id="0342d-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0342d-138">Code</span><span class="sxs-lookup"><span data-stu-id="0342d-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="0342d-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0342d-139">See also</span></span>
- <xref:System.Windows.IDataObject>
