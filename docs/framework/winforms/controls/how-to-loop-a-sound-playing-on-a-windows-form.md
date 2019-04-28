---
title: 'Vorgehensweise: Starten einer Schleife eines wiedergegebenen Sounds in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: a74acbbbcb5646a35de54a6000a0feae30f145a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638907"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="d3be7-102">Vorgehensweise: Starten einer Schleife eines wiedergegebenen Sounds in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3be7-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="d3be7-103">Im folgenden Codebeispiel wird ein Sound mehrfach wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="d3be7-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="d3be7-104">Wenn der Code im `stopPlayingButton_Click`-Ereignishandler ausgeführt wird, werden alle aktuell wiedergegebenen Sounds beendet.</span><span class="sxs-lookup"><span data-stu-id="d3be7-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="d3be7-105">Wenn kein Sound wiedergegeben wird, passiert nichts.</span><span class="sxs-lookup"><span data-stu-id="d3be7-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3be7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3be7-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d3be7-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d3be7-107">Compiling the Code</span></span>  
 <span data-ttu-id="d3be7-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d3be7-108">This example requires:</span></span>  
  
- <span data-ttu-id="d3be7-109">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="d3be7-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="d3be7-110">Ersetzen Sie den Dateinamen `"c:\Windows\Media\chimes.wav"` durch einen gültigen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="d3be7-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="d3be7-111">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d3be7-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d3be7-112">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="d3be7-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d3be7-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="d3be7-113">Robust Programming</span></span>  
 <span data-ttu-id="d3be7-114">Dateioperationen sollten in entsprechende Ausnahmebehandlungsblöcke eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="d3be7-114">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="d3be7-115">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="d3be7-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d3be7-116">Der Pfadname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="d3be7-116">The path name is malformed.</span></span> <span data-ttu-id="d3be7-117">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="d3be7-117">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="d3be7-118">Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="d3be7-118">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="d3be7-119">Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="d3be7-119">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="d3be7-120">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="d3be7-120">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="d3be7-121">Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="d3be7-121">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="d3be7-122">Der Pfad besteht nur aus einem Doppelpunkt ":" (<xref:System.NotSupportedException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="d3be7-122">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d3be7-123">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d3be7-123">.NET Framework Security</span></span>  
 <span data-ttu-id="d3be7-124">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="d3be7-124">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="d3be7-125">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="d3be7-125">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="d3be7-126">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3be7-126">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3be7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3be7-127">See also</span></span>

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="d3be7-128">Vorgehensweise: Wiedergabe von Sound in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3be7-128">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="d3be7-129">Übersicht über die SoundPlayer-Klasse</span><span class="sxs-lookup"><span data-stu-id="d3be7-129">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
