---
title: 'Gewusst wie: Lesen von Bildmetadaten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: cd3b636f8f0058d4a8eacc656f95d5f46b8967e2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040752"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="e1ff1-102">Gewusst wie: Lesen von Bildmetadaten</span><span class="sxs-lookup"><span data-stu-id="e1ff1-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="e1ff1-103">Einige Bilddateien enthalten Metadaten, die Sie lesen können, um die Funktionen des Images zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="e1ff1-104">Beispielsweise kann ein digitales Foto Metadaten enthalten, die Sie lesen können, um die Marke und das Modell der Kamera zu ermitteln, die zum Erfassen des Bilds verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="e1ff1-105">Mit GDI+ können Sie vorhandene Metadaten lesen, und Sie können auch neue Metadaten in Bilddateien schreiben.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="e1ff1-106">GDI+ speichert ein einzelnes Metadatenelement in einem <xref:System.Drawing.Imaging.PropertyItem> Objekt.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="e1ff1-107">Sie können die <xref:System.Drawing.Image.PropertyItems%2A>-Eigenschaft eines <xref:System.Drawing.Image> Objekts lesen, um alle Metadaten aus einer Datei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="e1ff1-108">Die <xref:System.Drawing.Image.PropertyItems%2A>-Eigenschaft gibt ein Array von <xref:System.Drawing.Imaging.PropertyItem>-Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="e1ff1-109">Ein <xref:System.Drawing.Imaging.PropertyItem>-Objekt verfügt über die folgenden vier Eigenschaften: `Id`, `Value`, `Len`und `Type`.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="e1ff1-110">Id</span><span class="sxs-lookup"><span data-stu-id="e1ff1-110">Id</span></span>

<span data-ttu-id="e1ff1-111">Ein-Tag, das das Metadatenelement bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="e1ff1-112">Einige Werte, die <xref:System.Drawing.Imaging.PropertyItem.Id%2A> zugewiesen werden können, sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e1ff1-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="e1ff1-113">Hexadezimalwert</span><span class="sxs-lookup"><span data-stu-id="e1ff1-113">Hexadecimal value</span></span>|<span data-ttu-id="e1ff1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ff1-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="e1ff1-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="e1ff1-115">0x0320</span></span><br /><br /> <span data-ttu-id="e1ff1-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="e1ff1-116">0x010F</span></span><br /><br /> <span data-ttu-id="e1ff1-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="e1ff1-117">0x0110</span></span><br /><br /> <span data-ttu-id="e1ff1-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="e1ff1-118">0x9003</span></span><br /><br /> <span data-ttu-id="e1ff1-119">0x829a</span><span class="sxs-lookup"><span data-stu-id="e1ff1-119">0x829A</span></span><br /><br /> <span data-ttu-id="e1ff1-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="e1ff1-120">0x5090</span></span><br /><br /> <span data-ttu-id="e1ff1-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="e1ff1-121">0x5091</span></span>|<span data-ttu-id="e1ff1-122">Image Titel</span><span class="sxs-lookup"><span data-stu-id="e1ff1-122">Image title</span></span><br /><br /> <span data-ttu-id="e1ff1-123">Gerätehersteller</span><span class="sxs-lookup"><span data-stu-id="e1ff1-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="e1ff1-124">Gerätemodell</span><span class="sxs-lookup"><span data-stu-id="e1ff1-124">Equipment model</span></span><br /><br /> <span data-ttu-id="e1ff1-125">EXIF-Original</span><span class="sxs-lookup"><span data-stu-id="e1ff1-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="e1ff1-126">EXIF-Anzeigezeit</span><span class="sxs-lookup"><span data-stu-id="e1ff1-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="e1ff1-127">Tabelle "Leuchtkraft"</span><span class="sxs-lookup"><span data-stu-id="e1ff1-127">Luminance table</span></span><br /><br /> <span data-ttu-id="e1ff1-128">Chrominance-Tabelle</span><span class="sxs-lookup"><span data-stu-id="e1ff1-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="e1ff1-129">Wert</span><span class="sxs-lookup"><span data-stu-id="e1ff1-129">Value</span></span>

<span data-ttu-id="e1ff1-130">Ein Array von-Werten.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-130">An array of values.</span></span> <span data-ttu-id="e1ff1-131">Das Format der Werte wird durch die <xref:System.Drawing.Imaging.PropertyItem.Type%2A>-Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="e1ff1-132">Len</span><span class="sxs-lookup"><span data-stu-id="e1ff1-132">Len</span></span>

<span data-ttu-id="e1ff1-133">Die Länge (in Byte) des Arrays von Werten, auf die von der <xref:System.Drawing.Imaging.PropertyItem.Value%2A>-Eigenschaft verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="e1ff1-134">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e1ff1-134">Type</span></span>

<span data-ttu-id="e1ff1-135">Der Datentyp der Werte im Array, auf die durch die `Value`-Eigenschaft verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="e1ff1-136">In der folgenden Tabelle sind die Formate aufgeführt, die durch die `Type`-Eigenschaftswerte angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="e1ff1-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="e1ff1-137">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="e1ff1-137">Numeric value</span></span>|<span data-ttu-id="e1ff1-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ff1-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="e1ff1-139">1</span><span class="sxs-lookup"><span data-stu-id="e1ff1-139">1</span></span>|<span data-ttu-id="e1ff1-140">Eine `Byte`</span><span class="sxs-lookup"><span data-stu-id="e1ff1-140">A `Byte`</span></span>|
|<span data-ttu-id="e1ff1-141">2</span><span class="sxs-lookup"><span data-stu-id="e1ff1-141">2</span></span>|<span data-ttu-id="e1ff1-142">Ein Array von `Byte` Objekten, die als ASCII codiert sind</span><span class="sxs-lookup"><span data-stu-id="e1ff1-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="e1ff1-143">3</span><span class="sxs-lookup"><span data-stu-id="e1ff1-143">3</span></span>|<span data-ttu-id="e1ff1-144">Eine 16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="e1ff1-144">A 16-bit integer</span></span>|
|<span data-ttu-id="e1ff1-145">4</span><span class="sxs-lookup"><span data-stu-id="e1ff1-145">4</span></span>|<span data-ttu-id="e1ff1-146">Eine 32-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="e1ff1-146">A 32-bit integer</span></span>|
|<span data-ttu-id="e1ff1-147">5</span><span class="sxs-lookup"><span data-stu-id="e1ff1-147">5</span></span>|<span data-ttu-id="e1ff1-148">Ein Array von zwei `Byte`-Objekten, die eine rationale Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="e1ff1-149">6</span><span class="sxs-lookup"><span data-stu-id="e1ff1-149">6</span></span>|<span data-ttu-id="e1ff1-150">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="e1ff1-150">Not used</span></span>|
|<span data-ttu-id="e1ff1-151">7</span><span class="sxs-lookup"><span data-stu-id="e1ff1-151">7</span></span>|<span data-ttu-id="e1ff1-152">Nicht definiert</span><span class="sxs-lookup"><span data-stu-id="e1ff1-152">Undefined</span></span>|
|<span data-ttu-id="e1ff1-153">8</span><span class="sxs-lookup"><span data-stu-id="e1ff1-153">8</span></span>|<span data-ttu-id="e1ff1-154">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="e1ff1-154">Not used</span></span>|
|<span data-ttu-id="e1ff1-155">9</span><span class="sxs-lookup"><span data-stu-id="e1ff1-155">9</span></span>|`SLong`|
|<span data-ttu-id="e1ff1-156">10</span><span class="sxs-lookup"><span data-stu-id="e1ff1-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="e1ff1-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1ff1-157">Example</span></span>
  
<span data-ttu-id="e1ff1-158">Im folgenden Codebeispiel werden die sieben Metadatenelemente in der Datei `FakePhoto.jpg`gelesen und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="e1ff1-159">Das zweite (Index 1)-Eigenschaften Element in der Liste hat <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Gerätehersteller) und <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-codiertes Bytearray).</span><span class="sxs-lookup"><span data-stu-id="e1ff1-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="e1ff1-160">Das Codebeispiel zeigt den Wert dieses Eigenschaften Elements an.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="e1ff1-161">Der Code erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e1ff1-161">The code produces output similar to the following:</span></span>

```output
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

## <a name="compiling-the-code"></a><span data-ttu-id="e1ff1-162">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e1ff1-162">Compiling the Code</span></span>

<span data-ttu-id="e1ff1-163">Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, bei dem es sich um einen Parameter des <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers handelt.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="e1ff1-164">Behandeln Sie das <xref:System.Windows.Forms.Control.Paint>-Ereignis des Formulars, und fügen Sie diesen Code in den Paint-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="e1ff1-165">Sie müssen `FakePhoto.jpg` durch einen in Ihrem System gültigen Bildnamen und Pfad ersetzen und den `System.Drawing.Imaging`-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="e1ff1-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1ff1-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1ff1-166">See also</span></span>

- [<span data-ttu-id="e1ff1-167">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="e1ff1-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="e1ff1-168">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="e1ff1-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
