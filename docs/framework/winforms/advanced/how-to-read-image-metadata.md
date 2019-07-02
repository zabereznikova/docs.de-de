---
title: 'Vorgehensweise: Lesen von Bildmetadaten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 6c02f7e5744828fd8eddc88be8d7da28f3bc2a2a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505777"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="eed87-102">Vorgehensweise: Lesen von Bildmetadaten</span><span class="sxs-lookup"><span data-stu-id="eed87-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="eed87-103">Einige Bilddateien enthalten Metadaten, die Sie lesen können, um zu bestimmen, Features des Abbilds an.</span><span class="sxs-lookup"><span data-stu-id="eed87-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="eed87-104">Beispielsweise kann eine digitale Fotografie Metadaten enthalten, die Sie lesen können, um zu bestimmen, die Marke und Modell der Kamera verwendet, um das Image zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="eed87-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="eed87-105">Mit GDI + können Sie vorhandene Metadaten gelesen, und Sie können auch neue Metadaten in Bilddateien schreiben.</span><span class="sxs-lookup"><span data-stu-id="eed87-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 <span data-ttu-id="eed87-106">GDI + speichert individuelle von Metadaten in einem <xref:System.Drawing.Imaging.PropertyItem> Objekt.</span><span class="sxs-lookup"><span data-stu-id="eed87-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="eed87-107">Erhalten Sie die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft eine <xref:System.Drawing.Image> Objekt, das alle Metadaten aus einer Datei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="eed87-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="eed87-108">Die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft gibt ein Array von <xref:System.Drawing.Imaging.PropertyItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="eed87-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="eed87-109">Ein <xref:System.Drawing.Imaging.PropertyItem> Objekt hat die folgenden vier Eigenschaften: `Id`, `Value`, `Len`, und `Type`.</span><span class="sxs-lookup"><span data-stu-id="eed87-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="eed87-110">Id</span><span class="sxs-lookup"><span data-stu-id="eed87-110">Id</span></span>  
 <span data-ttu-id="eed87-111">Ein Tag, der das Metadatenelement identifiziert.</span><span class="sxs-lookup"><span data-stu-id="eed87-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="eed87-112">Einige Werte, die zugewiesen werden können <xref:System.Drawing.Imaging.PropertyItem.Id%2A> werden in der folgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eed87-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="eed87-113">Hexadezimaler Wert</span><span class="sxs-lookup"><span data-stu-id="eed87-113">Hexadecimal value</span></span>|<span data-ttu-id="eed87-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eed87-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="eed87-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="eed87-115">0x0320</span></span><br /><br /> <span data-ttu-id="eed87-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="eed87-116">0x010F</span></span><br /><br /> <span data-ttu-id="eed87-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="eed87-117">0x0110</span></span><br /><br /> <span data-ttu-id="eed87-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="eed87-118">0x9003</span></span><br /><br /> <span data-ttu-id="eed87-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="eed87-119">0x829A</span></span><br /><br /> <span data-ttu-id="eed87-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="eed87-120">0x5090</span></span><br /><br /> <span data-ttu-id="eed87-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="eed87-121">0x5091</span></span>|<span data-ttu-id="eed87-122">Image-Titel</span><span class="sxs-lookup"><span data-stu-id="eed87-122">Image title</span></span><br /><br /> <span data-ttu-id="eed87-123">Originalgerätehersteller</span><span class="sxs-lookup"><span data-stu-id="eed87-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="eed87-124">Geräte-Modell</span><span class="sxs-lookup"><span data-stu-id="eed87-124">Equipment model</span></span><br /><br /> <span data-ttu-id="eed87-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="eed87-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="eed87-126">EXIF-Dauer</span><span class="sxs-lookup"><span data-stu-id="eed87-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="eed87-127">Luminanz-Tabelle</span><span class="sxs-lookup"><span data-stu-id="eed87-127">Luminance table</span></span><br /><br /> <span data-ttu-id="eed87-128">Chrominanz-Tabelle</span><span class="sxs-lookup"><span data-stu-id="eed87-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="eed87-129">Wert</span><span class="sxs-lookup"><span data-stu-id="eed87-129">Value</span></span>  
 <span data-ttu-id="eed87-130">Ein Array von Werten.</span><span class="sxs-lookup"><span data-stu-id="eed87-130">An array of values.</span></span> <span data-ttu-id="eed87-131">Das Format der Werte richtet sich nach der <xref:System.Drawing.Imaging.PropertyItem.Type%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eed87-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="eed87-132">Len</span><span class="sxs-lookup"><span data-stu-id="eed87-132">Len</span></span>  
 <span data-ttu-id="eed87-133">Die Zeitdauer (in Byte) das Array von Werten auf die von der <xref:System.Drawing.Imaging.PropertyItem.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eed87-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="eed87-134">Typ</span><span class="sxs-lookup"><span data-stu-id="eed87-134">Type</span></span>  
 <span data-ttu-id="eed87-135">Der Datentyp der Werte in das Array verweist die `Value` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eed87-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="eed87-136">Die Formate angegeben werden, indem die `Type` Eigenschaftswerte werden in der folgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eed87-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="eed87-137">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="eed87-137">Numeric value</span></span>|<span data-ttu-id="eed87-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eed87-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="eed87-139">1</span><span class="sxs-lookup"><span data-stu-id="eed87-139">1</span></span>|<span data-ttu-id="eed87-140">Eine `Byte`</span><span class="sxs-lookup"><span data-stu-id="eed87-140">A `Byte`</span></span>|  
|<span data-ttu-id="eed87-141">2</span><span class="sxs-lookup"><span data-stu-id="eed87-141">2</span></span>|<span data-ttu-id="eed87-142">Ein Array von `Byte` als ASCII-codierte Objekte</span><span class="sxs-lookup"><span data-stu-id="eed87-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="eed87-143">3</span><span class="sxs-lookup"><span data-stu-id="eed87-143">3</span></span>|<span data-ttu-id="eed87-144">Eine 16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="eed87-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="eed87-145">4</span><span class="sxs-lookup"><span data-stu-id="eed87-145">4</span></span>|<span data-ttu-id="eed87-146">Eine 32-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="eed87-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="eed87-147">5</span><span class="sxs-lookup"><span data-stu-id="eed87-147">5</span></span>|<span data-ttu-id="eed87-148">Ein Array mit zwei `Byte` eine rationale Zahl darstellende – Objekte</span><span class="sxs-lookup"><span data-stu-id="eed87-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="eed87-149">6</span><span class="sxs-lookup"><span data-stu-id="eed87-149">6</span></span>|<span data-ttu-id="eed87-150">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="eed87-150">Not used</span></span>|  
|<span data-ttu-id="eed87-151">7</span><span class="sxs-lookup"><span data-stu-id="eed87-151">7</span></span>|<span data-ttu-id="eed87-152">Nicht definiert</span><span class="sxs-lookup"><span data-stu-id="eed87-152">Undefined</span></span>|  
|<span data-ttu-id="eed87-153">8</span><span class="sxs-lookup"><span data-stu-id="eed87-153">8</span></span>|<span data-ttu-id="eed87-154">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="eed87-154">Not used</span></span>|  
|<span data-ttu-id="eed87-155">9</span><span class="sxs-lookup"><span data-stu-id="eed87-155">9</span></span>|`SLong`|  
|<span data-ttu-id="eed87-156">10</span><span class="sxs-lookup"><span data-stu-id="eed87-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="eed87-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eed87-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="eed87-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eed87-158">Description</span></span>  
 <span data-ttu-id="eed87-159">Das folgende Codebeispiel liest und zeigt die sieben Teile der Metadaten in der Datei `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="eed87-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="eed87-160">Das zweite Element der (Index 1)-Eigenschaft in der Liste hat <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Equipment Manufacturers, OEMs) und <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-codiertes Bytearray).</span><span class="sxs-lookup"><span data-stu-id="eed87-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="eed87-161">Das Codebeispiel zeigt den Wert des Eigenschaftenelements.</span><span class="sxs-lookup"><span data-stu-id="eed87-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="eed87-162">Der Code erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="eed87-162">The code produces output similar to the following:</span></span>  
 
```
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```
  
### <a name="code"></a><span data-ttu-id="eed87-163">Code</span><span class="sxs-lookup"><span data-stu-id="eed87-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eed87-164">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="eed87-164">Compiling the Code</span></span>  
 <span data-ttu-id="eed87-165">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="eed87-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="eed87-166">Behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis und fügen Sie diesen Code in Paint-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="eed87-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="eed87-167">Ersetzen Sie `FakePhoto.jpg` mit einem Image-Name und Pfad gültig ist, auf Ihrem System und Importieren der `System.Drawing.Imaging` Namespace.</span><span class="sxs-lookup"><span data-stu-id="eed87-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed87-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eed87-168">See also</span></span>

- [<span data-ttu-id="eed87-169">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="eed87-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="eed87-170">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="eed87-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
