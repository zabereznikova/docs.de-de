---
title: 'Vorgehensweise: Wiedergabe von Sound in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: 68a68f05b847877641132e540995f6b14bb6e065
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015802"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="8cc41-102">Vorgehensweise: Wiedergabe von Sound in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cc41-102">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="8cc41-103">In diesem Beispiel wird zur Laufzeit ein Sound in einem bestimmten Pfad wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="8cc41-103">This example plays a sound at a given path at run time.</span></span>

## <a name="example"></a><span data-ttu-id="8cc41-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8cc41-104">Example</span></span>

```vb
Sub PlaySimpleSound()
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")
End Sub
```

```csharp
private void playSimpleSound()
{
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");
    simpleSound.Play();
}
```

## <a name="compiling-the-code"></a><span data-ttu-id="8cc41-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8cc41-105">Compiling the Code</span></span>
 <span data-ttu-id="8cc41-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8cc41-106">This example requires:</span></span>

- <span data-ttu-id="8cc41-107">Ersetzen Sie den Dateinamen `"c:\Windows\Media\chimes.wav"` durch einen gültigen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="8cc41-107">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>

- <span data-ttu-id="8cc41-108">(C#) Ein Verweis auf den <xref:System.Media?displayProperty=nameWithType> -Namespace.</span><span class="sxs-lookup"><span data-stu-id="8cc41-108">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="8cc41-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8cc41-109">Robust Programming</span></span>
 <span data-ttu-id="8cc41-110">Dateivorgänge sollten in entsprechende strukturierte Ausnahmebehandlungsblöcke eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="8cc41-110">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>

 <span data-ttu-id="8cc41-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="8cc41-111">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="8cc41-112">Der Pfadname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="8cc41-112">The path name is malformed.</span></span> <span data-ttu-id="8cc41-113">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8cc41-113">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>

- <span data-ttu-id="8cc41-114">Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8cc41-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>

- <span data-ttu-id="8cc41-115">Der Pfadname ist `null` (<xref:System.ArgumentNullException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8cc41-115">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>

- <span data-ttu-id="8cc41-116">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8cc41-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>

- <span data-ttu-id="8cc41-117">Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8cc41-117">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>

- <span data-ttu-id="8cc41-118">Der Pfad ist nur ein Doppelpunkt, ":"<xref:System.NotSupportedException> (-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8cc41-118">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="8cc41-119">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8cc41-119">.NET Framework Security</span></span>
 <span data-ttu-id="8cc41-120">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="8cc41-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="8cc41-121">Bei der Datei `Form1.vb` handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="8cc41-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="8cc41-122">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cc41-122">Verify all inputs before using the data in your application.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cc41-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cc41-123">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="8cc41-124">Vorgehensweise: Asynchrones Laden eines Sounds in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="8cc41-124">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
