---
title: Wiedergabe von Sound (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a15efff54bd54fdaced6c741cd6acf5c8b544cdd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="50e24-102">Wiedergabe von Sound (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50e24-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="50e24-103">Das `My.Computer.Audio`-Objekt stellt Methoden zur Soundwiedergabe bereit.</span><span class="sxs-lookup"><span data-stu-id="50e24-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="50e24-104">Wiedergabe von Sound</span><span class="sxs-lookup"><span data-stu-id="50e24-104">Playing Sounds</span></span>  
 <span data-ttu-id="50e24-105">Die Wiedergabe im Hintergrund lässt die Anwendung einen anderen Code ausführen, während der Sound wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50e24-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="50e24-106">Die `My.Computer.Audio.Play`-Methode lässt die Anwendung nur einen Hintergrundsound gleichzeitig wiedergeben; wenn die Anwendung einen neuen Hintergrundsound wiedergibt, stoppt sie die Wiedergabe des vorherigen.</span><span class="sxs-lookup"><span data-stu-id="50e24-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="50e24-107">Sie können auch einen Sound wiedergeben und warten, bis er zu Ende ist.</span><span class="sxs-lookup"><span data-stu-id="50e24-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="50e24-108">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode einen Sound wieder.</span><span class="sxs-lookup"><span data-stu-id="50e24-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="50e24-109">Wenn `AudioPlayMode.WaitToComplete` angegeben wird, wartet `My.Computer.Audio.Play`, bis der Sound fertig ist, bevor der aufrufende Code fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="50e24-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="50e24-110">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass der Dateiname auf eine WAV-Sounddatei verweist, die sich auf Ihrem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="50e24-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 <span data-ttu-id="50e24-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="50e24-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span></span>  
  
 <span data-ttu-id="50e24-112">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode einen Sound wieder.</span><span class="sxs-lookup"><span data-stu-id="50e24-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="50e24-113">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass die Anwendungsressourcen eine WAV-Sounddatei mit dem Namen „Waterfall“ enthält.</span><span class="sxs-lookup"><span data-stu-id="50e24-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="50e24-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="50e24-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span></span>  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="50e24-115">Wiedergabe von Sound als Schleife</span><span class="sxs-lookup"><span data-stu-id="50e24-115">Playing Looping Sounds</span></span>  
 <span data-ttu-id="50e24-116">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode den angegebenen Sound im Hintergrund wieder, wenn `PlayMode.BackgroundLoop` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50e24-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="50e24-117">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass der Dateiname auf eine WAV-Sounddatei verweist, die sich auf Ihrem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="50e24-117">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 <span data-ttu-id="50e24-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="50e24-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span></span>  
  
 <span data-ttu-id="50e24-119">Im folgenden Beispiel gibt die `My.Computer.Audio.Play`-Methode den angegebenen Sound im Hintergrund wieder, wenn `PlayMode.BackgroundLoop` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50e24-119">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="50e24-120">Sie sollten beim Verwenden dieses Beispiels sicherstellen, dass die Anwendungsressourcen eine WAV-Sounddatei mit dem Namen „Waterfall“ enthält.</span><span class="sxs-lookup"><span data-stu-id="50e24-120">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="50e24-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="50e24-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span></span>  
  
 <span data-ttu-id="50e24-122">Das vorherige Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50e24-122">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="50e24-123">Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Sound**.</span><span class="sxs-lookup"><span data-stu-id="50e24-123">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="50e24-124">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="50e24-124">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="50e24-125">Wenn normalerweise eine Anwendung einen Sound als Schleife wiedergibt, sollte sie den Sound am Ende anhalten.</span><span class="sxs-lookup"><span data-stu-id="50e24-125">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="50e24-126">Beenden der Wiedergabe von Sound im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="50e24-126">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="50e24-127">Verwenden Sie die `My.Computer.Audio.Stop`-Methode, um den momentan im Hintergrund oder als Schleife wiedergegebenen Sound der Anwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="50e24-127">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="50e24-128">Wenn eine Anwendung einen Sound als Schleife wiedergibt, sollte sie den Sound normalerweise irgendwann anhalten.</span><span class="sxs-lookup"><span data-stu-id="50e24-128">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="50e24-129">Im folgenden Beispiel wird ein Sound, der im Hintergrund abgespielt wird, beendet.</span><span class="sxs-lookup"><span data-stu-id="50e24-129">The following example stops a sound that is playing in the background.</span></span>  
  
 <span data-ttu-id="50e24-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="50e24-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span></span>  
  
 <span data-ttu-id="50e24-131">Das vorherige Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50e24-131">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="50e24-132">Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Sound**.</span><span class="sxs-lookup"><span data-stu-id="50e24-132">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="50e24-133">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="50e24-133">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="50e24-134">Wiedergabe von Systemsound</span><span class="sxs-lookup"><span data-stu-id="50e24-134">Playing System Sounds</span></span>  
 <span data-ttu-id="50e24-135">Verwenden Sie die `My.Computer.Audio.PlaySystemSound`-Methode, um den angegebenen Systemsound wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="50e24-135">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="50e24-136">Die `My.Computer.Audio.PlaySystemSound`-Methode verwendet als Parameter einen der freigegebenen Member der <xref:System.Media.SystemSound>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="50e24-136">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="50e24-137">Der Systemsound <xref:System.Media.SystemSounds.Asterisk%2A> wird im Allgemeinen für Fehler verwendet.</span><span class="sxs-lookup"><span data-stu-id="50e24-137">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="50e24-138">Im folgenden Beispiel wird die `My.Computer.Audio.PlaySystemSound`-Methode verwendet, um einen Systemsound wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="50e24-138">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 <span data-ttu-id="50e24-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="50e24-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e24-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50e24-140">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>

