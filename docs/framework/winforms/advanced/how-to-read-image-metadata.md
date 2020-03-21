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
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182520"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="a29b3-102">Gewusst wie: Lesen von Bildmetadaten</span><span class="sxs-lookup"><span data-stu-id="a29b3-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="a29b3-103">Einige Bilddateien enthalten Metadaten, die Sie lesen können, um die Features des Bildes zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a29b3-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="a29b3-104">Ein digitales Foto kann z. B. Metadaten enthalten, die Sie lesen können, um die Herstellung und das Modell der Kamera zu bestimmen, die zum Aufnehmen des Bildes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a29b3-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="a29b3-105">Mit GDI+ können Sie vorhandene Metadaten lesen und auch neue Metadaten in Bilddateien schreiben.</span><span class="sxs-lookup"><span data-stu-id="a29b3-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="a29b3-106">GDI+ speichert einzelne Metadaten in <xref:System.Drawing.Imaging.PropertyItem> einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="a29b3-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="a29b3-107">Sie können <xref:System.Drawing.Image.PropertyItems%2A> die Eigenschaft <xref:System.Drawing.Image> eines Objekts lesen, um alle Metadaten aus einer Datei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a29b3-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="a29b3-108">Die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft gibt <xref:System.Drawing.Imaging.PropertyItem> ein Array von Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="a29b3-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="a29b3-109">Ein <xref:System.Drawing.Imaging.PropertyItem> Objekt weist die `Id`folgenden `Value` `Len`vier `Type`Eigenschaften auf: , , und .</span><span class="sxs-lookup"><span data-stu-id="a29b3-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="a29b3-110">Id</span><span class="sxs-lookup"><span data-stu-id="a29b3-110">Id</span></span>

<span data-ttu-id="a29b3-111">Ein Tag, das das Metadatenelement identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a29b3-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="a29b3-112">Einige Werte, denen <xref:System.Drawing.Imaging.PropertyItem.Id%2A> zugewiesen werden kann, sind in der folgenden Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a29b3-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="a29b3-113">Hexadezimalwert</span><span class="sxs-lookup"><span data-stu-id="a29b3-113">Hexadecimal value</span></span>|<span data-ttu-id="a29b3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a29b3-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="a29b3-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="a29b3-115">0x0320</span></span><br /><br /> <span data-ttu-id="a29b3-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="a29b3-116">0x010F</span></span><br /><br /> <span data-ttu-id="a29b3-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="a29b3-117">0x0110</span></span><br /><br /> <span data-ttu-id="a29b3-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="a29b3-118">0x9003</span></span><br /><br /> <span data-ttu-id="a29b3-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="a29b3-119">0x829A</span></span><br /><br /> <span data-ttu-id="a29b3-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="a29b3-120">0x5090</span></span><br /><br /> <span data-ttu-id="a29b3-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="a29b3-121">0x5091</span></span>|<span data-ttu-id="a29b3-122">Bildtitel</span><span class="sxs-lookup"><span data-stu-id="a29b3-122">Image title</span></span><br /><br /> <span data-ttu-id="a29b3-123">Gerätehersteller</span><span class="sxs-lookup"><span data-stu-id="a29b3-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="a29b3-124">Gerätemodell</span><span class="sxs-lookup"><span data-stu-id="a29b3-124">Equipment model</span></span><br /><br /> <span data-ttu-id="a29b3-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="a29b3-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="a29b3-126">Exif Belichtungszeit</span><span class="sxs-lookup"><span data-stu-id="a29b3-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="a29b3-127">Luminanztabelle</span><span class="sxs-lookup"><span data-stu-id="a29b3-127">Luminance table</span></span><br /><br /> <span data-ttu-id="a29b3-128">Chrominanztabelle</span><span class="sxs-lookup"><span data-stu-id="a29b3-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="a29b3-129">value</span><span class="sxs-lookup"><span data-stu-id="a29b3-129">Value</span></span>

<span data-ttu-id="a29b3-130">Ein Array von -Werten.</span><span class="sxs-lookup"><span data-stu-id="a29b3-130">An array of values.</span></span> <span data-ttu-id="a29b3-131">Das Format der Werte wird <xref:System.Drawing.Imaging.PropertyItem.Type%2A> durch die Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a29b3-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="a29b3-132">Len</span><span class="sxs-lookup"><span data-stu-id="a29b3-132">Len</span></span>

<span data-ttu-id="a29b3-133">Die Länge (in Bytes) des Arrays <xref:System.Drawing.Imaging.PropertyItem.Value%2A> von Werten, auf das die Eigenschaft zeigt.</span><span class="sxs-lookup"><span data-stu-id="a29b3-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="a29b3-134">type</span><span class="sxs-lookup"><span data-stu-id="a29b3-134">Type</span></span>

<span data-ttu-id="a29b3-135">Der Datentyp der Werte im Array, `Value` auf die die Eigenschaft zeigt.</span><span class="sxs-lookup"><span data-stu-id="a29b3-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="a29b3-136">Die durch die `Type` Eigenschaftswerte angegebenen Formate werden in der folgenden Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a29b3-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="a29b3-137">Numerischer Wert</span><span class="sxs-lookup"><span data-stu-id="a29b3-137">Numeric value</span></span>|<span data-ttu-id="a29b3-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a29b3-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="a29b3-139">1</span><span class="sxs-lookup"><span data-stu-id="a29b3-139">1</span></span>|<span data-ttu-id="a29b3-140">A `Byte`</span><span class="sxs-lookup"><span data-stu-id="a29b3-140">A `Byte`</span></span>|
|<span data-ttu-id="a29b3-141">2</span><span class="sxs-lookup"><span data-stu-id="a29b3-141">2</span></span>|<span data-ttu-id="a29b3-142">Ein Array `Byte` von Objekten, die als ASCII kodiert sind</span><span class="sxs-lookup"><span data-stu-id="a29b3-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="a29b3-143">3</span><span class="sxs-lookup"><span data-stu-id="a29b3-143">3</span></span>|<span data-ttu-id="a29b3-144">Eine 16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="a29b3-144">A 16-bit integer</span></span>|
|<span data-ttu-id="a29b3-145">4</span><span class="sxs-lookup"><span data-stu-id="a29b3-145">4</span></span>|<span data-ttu-id="a29b3-146">Eine 32-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="a29b3-146">A 32-bit integer</span></span>|
|<span data-ttu-id="a29b3-147">5</span><span class="sxs-lookup"><span data-stu-id="a29b3-147">5</span></span>|<span data-ttu-id="a29b3-148">Ein Array `Byte` von zwei Objekten, die eine rationale Zahl darstellen</span><span class="sxs-lookup"><span data-stu-id="a29b3-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="a29b3-149">6</span><span class="sxs-lookup"><span data-stu-id="a29b3-149">6</span></span>|<span data-ttu-id="a29b3-150">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="a29b3-150">Not used</span></span>|
|<span data-ttu-id="a29b3-151">7</span><span class="sxs-lookup"><span data-stu-id="a29b3-151">7</span></span>|<span data-ttu-id="a29b3-152">Nicht definiert</span><span class="sxs-lookup"><span data-stu-id="a29b3-152">Undefined</span></span>|
|<span data-ttu-id="a29b3-153">8</span><span class="sxs-lookup"><span data-stu-id="a29b3-153">8</span></span>|<span data-ttu-id="a29b3-154">Nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="a29b3-154">Not used</span></span>|
|<span data-ttu-id="a29b3-155">9</span><span class="sxs-lookup"><span data-stu-id="a29b3-155">9</span></span>|`SLong`|
|<span data-ttu-id="a29b3-156">10</span><span class="sxs-lookup"><span data-stu-id="a29b3-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="a29b3-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a29b3-157">Example</span></span>
  
<span data-ttu-id="a29b3-158">Im folgenden Codebeispiel werden die sieben Metadaten `FakePhoto.jpg`in der Datei gelesen und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a29b3-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="a29b3-159">Das zweite Eigenschaftselement (Index 1) in der Liste enthält <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Gerätehersteller) und <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-codiertes Byte-Array).</span><span class="sxs-lookup"><span data-stu-id="a29b3-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="a29b3-160">Im Codebeispiel wird der Wert dieses Eigenschaftselements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a29b3-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="a29b3-161">Der Code erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="a29b3-161">The code produces output similar to the following:</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="a29b3-162">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a29b3-162">Compiling the Code</span></span>

<span data-ttu-id="a29b3-163">Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.Control.Paint> konzipiert und erfordert , was ein Parameter des Ereignishandlers ist.</span><span class="sxs-lookup"><span data-stu-id="a29b3-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="a29b3-164">Behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis des Formulars, und fügen Sie diesen Code in den paint-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="a29b3-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="a29b3-165">Sie müssen `FakePhoto.jpg` einen auf Ihrem System gültigen Bildnamen `System.Drawing.Imaging` und Pfad ersetzen und den Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="a29b3-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="a29b3-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a29b3-166">See also</span></span>

- [<span data-ttu-id="a29b3-167">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="a29b3-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="a29b3-168">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="a29b3-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
