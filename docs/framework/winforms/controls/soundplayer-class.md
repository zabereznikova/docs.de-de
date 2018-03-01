---
title: SoundPlayer-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SoundPlayer
helpviewer_keywords:
- sounds [Windows Forms], playing
ms.assetid: f3945af9-045c-4e2d-b251-377c37ca2d77
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5379da3361a8a4b2115f46d0d2db80a565f6bfc9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="soundplayer-class"></a><span data-ttu-id="4ce56-102">SoundPlayer-Klasse</span><span class="sxs-lookup"><span data-stu-id="4ce56-102">SoundPlayer Class</span></span>
<span data-ttu-id="4ce56-103">Die `SoundPlayer`-Klasse ermöglicht es Ihnen, Sounds problemlos in Ihre Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="4ce56-103">The `SoundPlayer` class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="4ce56-104">Sie können auch die <xref:System.Media.SystemSounds>-Klasse verwenden, um allgemeine Systemsounds wiederzugeben, einschließlich eines akustischen Signals.</span><span class="sxs-lookup"><span data-stu-id="4ce56-104">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ce56-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4ce56-105">In This Section</span></span>  
 [<span data-ttu-id="4ce56-106">Übersicht über die SoundPlayer-Klasse</span><span class="sxs-lookup"><span data-stu-id="4ce56-106">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)  
 <span data-ttu-id="4ce56-107">Stellt die Klasse und die am häufigsten verwendeten Eigenschaften, Methoden und Ereignisse vor.</span><span class="sxs-lookup"><span data-stu-id="4ce56-107">Introduces the class and its commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="4ce56-108">Gewusst wie: Wiedergabe von Sound in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ce56-108">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 <span data-ttu-id="4ce56-109">Stellt Code zum Abspielen eines Sounds bereit, der über einen Dateipfad, UNC-Pfad oder HTTP-Pfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4ce56-109">Provides code to play a sound specified via a file path, UNC path, or HTTP path.</span></span>  
  
 [<span data-ttu-id="4ce56-110">Gewusst wie: Wiedergabe eines Signaltons in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ce56-110">How to: Play a Beep from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)  
 <span data-ttu-id="4ce56-111">Stellt Code zum Wiedergeben des Signaltons des Computers bereit.</span><span class="sxs-lookup"><span data-stu-id="4ce56-111">Provides code to play the computer's beep sound.</span></span>  
  
 [<span data-ttu-id="4ce56-112">Gewusst wie: Wiedergeben eines in einer Ressource aus Windows Form eingebetteten Sounds</span><span class="sxs-lookup"><span data-stu-id="4ce56-112">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form.md)  
 <span data-ttu-id="4ce56-113">Stellt Code zum Wiedergeben eines Sounds über eine Ressource bereit.</span><span class="sxs-lookup"><span data-stu-id="4ce56-113">Provides code to play a sound from a resource.</span></span>  
  
 [<span data-ttu-id="4ce56-114">Gewusst wie: Wiedergabe eines Systemsounds in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ce56-114">How to: Play a System Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 <span data-ttu-id="4ce56-115">Stellt Code zum Wiedergeben eines Systemsounds bereit.</span><span class="sxs-lookup"><span data-stu-id="4ce56-115">Provides code to play the one of the system sounds.</span></span>  
  
 [<span data-ttu-id="4ce56-116">Gewusst wie: Asynchrones Laden eines Sounds in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="4ce56-116">How to: Load a Sound Asynchronously within a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)  
 <span data-ttu-id="4ce56-117">Stellt Code zum asynchronen Laden eines Sounds aus einer URL und für dessen Wiedergabe bereit.</span><span class="sxs-lookup"><span data-stu-id="4ce56-117">Provides code to load a sound asynchronously from a URL and play it.</span></span>  
  
 [<span data-ttu-id="4ce56-118">Gewusst wie: Starten einer Schleife eines wiedergegebenen Sounds in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4ce56-118">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)  
 <span data-ttu-id="4ce56-119">Stellt Code zum wiederholten Wiedergeben eines Sounds bereit.</span><span class="sxs-lookup"><span data-stu-id="4ce56-119">Provides code that plays a sound repeatedly.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4ce56-120">Verweis</span><span class="sxs-lookup"><span data-stu-id="4ce56-120">Reference</span></span>  
 <xref:System.Media.SoundPlayer>  
 <span data-ttu-id="4ce56-121">Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="4ce56-121">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ce56-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4ce56-122">Related Sections</span></span>  
 [<span data-ttu-id="4ce56-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="4ce56-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="4ce56-124">Enthält Links zu Themen über Steuerelemente, die speziell für Windows Forms vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="4ce56-124">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="4ce56-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="4ce56-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="4ce56-126">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="4ce56-126">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 <span data-ttu-id="4ce56-127">Siehe auch [HYPERLINK "http://msdn.microsoft.com/library/11bxex12 (110)" My.Computer-Objekt](http://msdn.microsoft.com/library/11bxex12\(v=vs.110\)) oder [My.Computer-Objekt](http://msdn.microsoft.com/library/11bxex12\(v=vs.120\)).</span><span class="sxs-lookup"><span data-stu-id="4ce56-127">Also see [HYPERLINK "http://msdn.microsoft.com/library/11bxex12(v=vs.110)" My.Computer Object](http://msdn.microsoft.com/library/11bxex12\(v=vs.110\)) or [My.Computer Object](http://msdn.microsoft.com/library/11bxex12\(v=vs.120\)).</span></span>
