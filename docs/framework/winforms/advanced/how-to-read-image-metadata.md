---
title: 'Gewusst wie: Lesen von Bildmetadaten'
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
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9df2866251e08b8989f8550d045b587c9de8d2cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="615bf-102">Gewusst wie: Lesen von Bildmetadaten</span><span class="sxs-lookup"><span data-stu-id="615bf-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="615bf-103">Einige Bilddateien enthalten Metadaten, die Sie lesen können, um zu bestimmen, die Funktionen des Bilds.</span><span class="sxs-lookup"><span data-stu-id="615bf-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="615bf-104">Angenommen, enthält ein digitales Foto Metadaten, die Sie lesen können, um zu bestimmen, den Hersteller und Modell der Kamera verwendet, um das Abbild aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="615bf-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="615bf-105">Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie vorhandene Metadaten gelesen, und Sie können auch neue Metadaten in Bilddateien geschrieben.</span><span class="sxs-lookup"><span data-stu-id="615bf-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="615bf-106">Speichert ein einzelnes Stück von Metadaten in einem <xref:System.Drawing.Imaging.PropertyItem> Objekt.</span><span class="sxs-lookup"><span data-stu-id="615bf-106"> stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="615bf-107">Informieren Sie sich die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft ein <xref:System.Drawing.Image> Objekt, das alle Metadaten aus einer Datei abrufen.</span><span class="sxs-lookup"><span data-stu-id="615bf-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="615bf-108">Die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft gibt ein Array von <xref:System.Drawing.Imaging.PropertyItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="615bf-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="615bf-109">Ein <xref:System.Drawing.Imaging.PropertyItem> Objekt hat die folgenden vier Eigenschaften: `Id`, `Value`, `Len`, und `Type`.</span><span class="sxs-lookup"><span data-stu-id="615bf-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="615bf-110">ID</span><span class="sxs-lookup"><span data-stu-id="615bf-110">Id</span></span>  
 <span data-ttu-id="615bf-111">Ein Tag, das Metadatenelement identifiziert.</span><span class="sxs-lookup"><span data-stu-id="615bf-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="615bf-112">Einige Werte, die zugewiesen werden können <xref:System.Drawing.Imaging.PropertyItem.Id%2A> sind in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="615bf-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="615bf-113">Hexadezimalwert</span><span class="sxs-lookup"><span data-stu-id="615bf-113">Hexadecimal value</span></span>|<span data-ttu-id="615bf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="615bf-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="615bf-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="615bf-115">0x0320</span></span><br /><br /> <span data-ttu-id="615bf-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="615bf-116">0x010F</span></span><br /><br /> <span data-ttu-id="615bf-117">0 x 0110</span><span class="sxs-lookup"><span data-stu-id="615bf-117">0x0110</span></span><br /><br /> <span data-ttu-id="615bf-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="615bf-118">0x9003</span></span><br /><br /> <span data-ttu-id="615bf-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="615bf-119">0x829A</span></span><br /><br /> <span data-ttu-id="615bf-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="615bf-120">0x5090</span></span><br /><br /> <span data-ttu-id="615bf-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="615bf-121">0x5091</span></span>|<span data-ttu-id="615bf-122">Image-Titel</span><span class="sxs-lookup"><span data-stu-id="615bf-122">Image title</span></span><br /><br /> <span data-ttu-id="615bf-123">Gerätehersteller</span><span class="sxs-lookup"><span data-stu-id="615bf-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="615bf-124">Geräte-Modell</span><span class="sxs-lookup"><span data-stu-id="615bf-124">Equipment model</span></span><br /><br /> <span data-ttu-id="615bf-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="615bf-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="615bf-126">EXIF Offenlegung Zeit</span><span class="sxs-lookup"><span data-stu-id="615bf-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="615bf-127">Intensität-Tabelle</span><span class="sxs-lookup"><span data-stu-id="615bf-127">Luminance table</span></span><br /><br /> <span data-ttu-id="615bf-128">Chrominanz-Tabelle</span><span class="sxs-lookup"><span data-stu-id="615bf-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="615bf-129">Wert</span><span class="sxs-lookup"><span data-stu-id="615bf-129">Value</span></span>  
 <span data-ttu-id="615bf-130">Ein Array von Werten.</span><span class="sxs-lookup"><span data-stu-id="615bf-130">An array of values.</span></span> <span data-ttu-id="615bf-131">Das Format der Werte wird bestimmt, indem die <xref:System.Drawing.Imaging.PropertyItem.Type%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="615bf-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="615bf-132">Len</span><span class="sxs-lookup"><span data-stu-id="615bf-132">Len</span></span>  
 <span data-ttu-id="615bf-133">Die Länge (in Bytes) des Arrays von Werten verweist die <xref:System.Drawing.Imaging.PropertyItem.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="615bf-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="615bf-134">Typ</span><span class="sxs-lookup"><span data-stu-id="615bf-134">Type</span></span>  
 <span data-ttu-id="615bf-135">Der Datentyp der Werte im Array verweist die `Value` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="615bf-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="615bf-136">Die Formate angegeben werden, durch die `Type` Eigenschaftswerte werden in der folgenden Tabelle angezeigt</span><span class="sxs-lookup"><span data-stu-id="615bf-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="615bf-137">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="615bf-137">Numeric value</span></span>|<span data-ttu-id="615bf-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="615bf-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="615bf-139">1</span><span class="sxs-lookup"><span data-stu-id="615bf-139">1</span></span>|<span data-ttu-id="615bf-140">Eine `Byte`</span><span class="sxs-lookup"><span data-stu-id="615bf-140">A `Byte`</span></span>|  
|<span data-ttu-id="615bf-141">2</span><span class="sxs-lookup"><span data-stu-id="615bf-141">2</span></span>|<span data-ttu-id="615bf-142">Ein Array von `Byte` als ASCII-codierte Objekte</span><span class="sxs-lookup"><span data-stu-id="615bf-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="615bf-143">3</span><span class="sxs-lookup"><span data-stu-id="615bf-143">3</span></span>|<span data-ttu-id="615bf-144">Eine 16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="615bf-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="615bf-145">4</span><span class="sxs-lookup"><span data-stu-id="615bf-145">4</span></span>|<span data-ttu-id="615bf-146">Eine 32-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="615bf-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="615bf-147">5</span><span class="sxs-lookup"><span data-stu-id="615bf-147">5</span></span>|<span data-ttu-id="615bf-148">Ein Array mit zwei `Byte` Objekte, die eine rationale Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="615bf-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="615bf-149">6</span><span class="sxs-lookup"><span data-stu-id="615bf-149">6</span></span>|<span data-ttu-id="615bf-150">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="615bf-150">Not used</span></span>|  
|<span data-ttu-id="615bf-151">7</span><span class="sxs-lookup"><span data-stu-id="615bf-151">7</span></span>|<span data-ttu-id="615bf-152">Nicht definiert</span><span class="sxs-lookup"><span data-stu-id="615bf-152">Undefined</span></span>|  
|<span data-ttu-id="615bf-153">8</span><span class="sxs-lookup"><span data-stu-id="615bf-153">8</span></span>|<span data-ttu-id="615bf-154">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="615bf-154">Not used</span></span>|  
|<span data-ttu-id="615bf-155">9</span><span class="sxs-lookup"><span data-stu-id="615bf-155">9</span></span>|`SLong`|  
|<span data-ttu-id="615bf-156">10</span><span class="sxs-lookup"><span data-stu-id="615bf-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="615bf-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="615bf-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="615bf-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="615bf-158">Description</span></span>  
 <span data-ttu-id="615bf-159">Im folgenden Codebeispiel wird liest und zeigt die sieben Teile von Metadaten in der Datei `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="615bf-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="615bf-160">Das zweite Element der (Index 1)-Eigenschaft in der Liste hat <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Gerätehersteller) und <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-codiertes Bytearray).</span><span class="sxs-lookup"><span data-stu-id="615bf-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="615bf-161">Das Codebeispiel zeigt den Wert des Eigenschaftenelements.</span><span class="sxs-lookup"><span data-stu-id="615bf-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="615bf-162">Der Code erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="615bf-162">The code produces output similar to the following:</span></span>  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a><span data-ttu-id="615bf-163">Code</span><span class="sxs-lookup"><span data-stu-id="615bf-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="615bf-164">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="615bf-164">Compiling the Code</span></span>  
 <span data-ttu-id="615bf-165">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="615bf-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="615bf-166">Behandeln des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis und fügen Sie diesen Code in den Paint-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="615bf-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="615bf-167">Ersetzen Sie `FakePhoto.jpg` mit einem Image-Name und Pfad gültig ist, auf Ihrem System und Importieren der `System.Drawing.Imaging` Namespace.</span><span class="sxs-lookup"><span data-stu-id="615bf-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615bf-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="615bf-168">See Also</span></span>  
 [<span data-ttu-id="615bf-169">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="615bf-169">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="615bf-170">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="615bf-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
