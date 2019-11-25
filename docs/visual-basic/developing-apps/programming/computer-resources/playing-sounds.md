---
title: Wiedergabe von Sound
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: 416fedd011ff35d2b32d1b64932e3908a73ed14e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345523"
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="867d4-102">Wiedergabe von Sound (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="867d4-102">Playing Sounds (Visual Basic)</span></span>

<span data-ttu-id="867d4-103">Das `My.Computer.Audio`-Objekt stellt Methoden zur Soundwiedergabe bereit.</span><span class="sxs-lookup"><span data-stu-id="867d4-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="867d4-104">Wiedergabe von Sound</span><span class="sxs-lookup"><span data-stu-id="867d4-104">Playing Sounds</span></span>  

 <span data-ttu-id="867d4-105">Die Wiedergabe im Hintergrund lässt die Anwendung einen anderen Code ausführen, während der Sound wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="867d4-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="867d4-106">Die `My.Computer.Audio.Play`-Methode lässt die Anwendung nur einen Hintergrundsound gleichzeitig wiedergeben; wenn die Anwendung einen neuen Hintergrundsound wiedergibt, stoppt sie die Wiedergabe des vorherigen.</span><span class="sxs-lookup"><span data-stu-id="867d4-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="867d4-107">Sie können auch einen Sound wiedergeben und warten, bis er zu Ende ist.</span><span class="sxs-lookup"><span data-stu-id="867d4-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="867d4-108">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode einen Sound wieder.</span><span class="sxs-lookup"><span data-stu-id="867d4-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="867d4-109">Wenn `AudioPlayMode.WaitToComplete` angegeben wird, wartet `My.Computer.Audio.Play`, bis der Sound fertig ist, bevor der aufrufende Code fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="867d4-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="867d4-110">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass der Dateiname auf eine WAV-Sounddatei verweist, die sich auf Ihrem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="867d4-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 <span data-ttu-id="867d4-111">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode einen Sound wieder.</span><span class="sxs-lookup"><span data-stu-id="867d4-111">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="867d4-112">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass die Anwendungsressourcen eine WAV-Sounddatei mit dem Namen „Waterfall“ enthält.</span><span class="sxs-lookup"><span data-stu-id="867d4-112">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="867d4-113">Wiedergabe von Sound als Schleife</span><span class="sxs-lookup"><span data-stu-id="867d4-113">Playing Looping Sounds</span></span>  

 <span data-ttu-id="867d4-114">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode den angegebenen Sound im Hintergrund wieder, wenn `PlayMode.BackgroundLoop` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="867d4-114">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="867d4-115">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass der Dateiname auf eine WAV-Sounddatei verweist, die sich auf Ihrem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="867d4-115">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 <span data-ttu-id="867d4-116">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode den angegebenen Sound im Hintergrund wieder, wenn `PlayMode.BackgroundLoop` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="867d4-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="867d4-117">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass die Anwendungsressourcen eine WAV-Sounddatei mit dem Namen „Waterfall“ enthält.</span><span class="sxs-lookup"><span data-stu-id="867d4-117">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 <span data-ttu-id="867d4-118">Das vorherige Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="867d4-118">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="867d4-119">Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Sound**.</span><span class="sxs-lookup"><span data-stu-id="867d4-119">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="867d4-120">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="867d4-120">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="867d4-121">Wenn normalerweise eine Anwendung einen Sound als Schleife wiedergibt, sollte sie den Sound am Ende anhalten.</span><span class="sxs-lookup"><span data-stu-id="867d4-121">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="867d4-122">Beenden der Wiedergabe von Sound im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="867d4-122">Stopping the Playing of Sounds in the Background</span></span>  

 <span data-ttu-id="867d4-123">Verwenden Sie die `My.Computer.Audio.Stop`-Methode, um den momentan im Hintergrund oder als Schleife wiedergegebenen Sound der Anwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="867d4-123">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="867d4-124">Wenn eine Anwendung einen Sound als Schleife wiedergibt, sollte sie den Sound normalerweise irgendwann anhalten.</span><span class="sxs-lookup"><span data-stu-id="867d4-124">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="867d4-125">Im folgenden Beispiel wird ein Sound, der im Hintergrund abgespielt wird, beendet.</span><span class="sxs-lookup"><span data-stu-id="867d4-125">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 <span data-ttu-id="867d4-126">Das vorherige Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="867d4-126">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="867d4-127">Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Sound**.</span><span class="sxs-lookup"><span data-stu-id="867d4-127">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="867d4-128">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="867d4-128">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="867d4-129">Wiedergabe von Systemsound</span><span class="sxs-lookup"><span data-stu-id="867d4-129">Playing System Sounds</span></span>  

 <span data-ttu-id="867d4-130">Verwenden Sie die `My.Computer.Audio.PlaySystemSound`-Methode, um den angegebenen Systemsound wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="867d4-130">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="867d4-131">Die `My.Computer.Audio.PlaySystemSound`-Methode verwendet als Parameter einen der freigegebenen Member der <xref:System.Media.SystemSound>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="867d4-131">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="867d4-132">Der Systemsound <xref:System.Media.SystemSounds.Asterisk%2A> wird im Allgemeinen für Fehler verwendet.</span><span class="sxs-lookup"><span data-stu-id="867d4-132">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="867d4-133">Im folgenden Beispiel wird die `My.Computer.Audio.PlaySystemSound`-Methode verwendet, um einen Systemsound wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="867d4-133">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="867d4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="867d4-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
