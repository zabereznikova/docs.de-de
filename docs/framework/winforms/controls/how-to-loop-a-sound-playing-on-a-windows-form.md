---
title: 'Vorgehensweise: Schleife ein wiedergegebenen Sounds in Windows Forms'
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
ms.openlocfilehash: 93793fae418b33c954c9d597f020c8daf8cfedfd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493403"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="b2987-102">Vorgehensweise: Schleife ein wiedergegebenen Sounds in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2987-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="b2987-103">Im folgenden Codebeispiel wird ein Sound mehrfach wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b2987-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="b2987-104">Wenn der Code im `stopPlayingButton_Click`-Ereignishandler ausgeführt wird, werden alle aktuell wiedergegebenen Sounds beendet.</span><span class="sxs-lookup"><span data-stu-id="b2987-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="b2987-105">Wenn kein Sound wiedergegeben wird, passiert nichts.</span><span class="sxs-lookup"><span data-stu-id="b2987-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2987-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2987-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2987-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b2987-107">Compiling the Code</span></span>  
 <span data-ttu-id="b2987-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b2987-108">This example requires:</span></span>  
  
-   <span data-ttu-id="b2987-109">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="b2987-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="b2987-110">Ersetzen Sie den Dateinamen `"c:\Windows\Media\chimes.wav"` durch einen gültigen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="b2987-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="b2987-111">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b2987-111">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b2987-112">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2987-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b2987-113">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b2987-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b2987-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b2987-114">Robust Programming</span></span>  
 <span data-ttu-id="b2987-115">Dateioperationen sollten in entsprechende Ausnahmebehandlungsblöcke eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="b2987-115">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="b2987-116">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="b2987-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b2987-117">Der Pfadname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="b2987-117">The path name is malformed.</span></span> <span data-ttu-id="b2987-118">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="b2987-118">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="b2987-119">Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="b2987-119">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="b2987-120">Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="b2987-120">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="b2987-121">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="b2987-121">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="b2987-122">Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="b2987-122">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="b2987-123">Der Pfad besteht nur aus einem Doppelpunkt ":" (<xref:System.NotSupportedException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="b2987-123">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b2987-124">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b2987-124">.NET Framework Security</span></span>  
 <span data-ttu-id="b2987-125">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="b2987-125">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="b2987-126">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="b2987-126">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="b2987-127">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2987-127">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2987-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2987-128">See also</span></span>
- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="b2987-129">Vorgehensweise: Wiedergabe von Sound in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2987-129">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="b2987-130">Übersicht über die SoundPlayer-Klasse</span><span class="sxs-lookup"><span data-stu-id="b2987-130">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)
