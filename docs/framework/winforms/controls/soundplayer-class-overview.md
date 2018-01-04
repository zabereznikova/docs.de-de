---
title: "Übersicht über die SoundPlayer-Klasse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dc355fbe0d8262cb24779b99375d6075f758bbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="60cc8-102">Übersicht über die SoundPlayer-Klasse</span><span class="sxs-lookup"><span data-stu-id="60cc8-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="60cc8-103">Die <xref:System.Media.SoundPlayer>-Klasse ermöglicht es Ihnen, Sounds problemlos in Ihre Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="60cc8-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="60cc8-104">Die <xref:System.Media.SoundPlayer> Klasse Audiodateien im WAV-Format aus einer Ressource oder UNC-Namen oder HTTP-Speicherorte wiedergeben kann.</span><span class="sxs-lookup"><span data-stu-id="60cc8-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="60cc8-105">Darüber hinaus die <xref:System.Media.SoundPlayer> -Klasse ermöglicht es Ihnen zu laden oder Wiedergeben von Sounds asynchron.</span><span class="sxs-lookup"><span data-stu-id="60cc8-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="60cc8-106">Sie können auch die <xref:System.Media.SystemSounds>-Klasse verwenden, um allgemeine Systemsounds wiederzugeben, einschließlich eines akustischen Signals.</span><span class="sxs-lookup"><span data-stu-id="60cc8-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="60cc8-107">Häufig verwendete Eigenschaften, Methoden und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="60cc8-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="60cc8-108">name</span><span class="sxs-lookup"><span data-stu-id="60cc8-108">Name</span></span>|<span data-ttu-id="60cc8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60cc8-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="60cc8-110"><xref:System.Media.SoundPlayer.SoundLocation%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="60cc8-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="60cc8-111">Der Dateipfad oder die Webadresse des Sounds.</span><span class="sxs-lookup"><span data-stu-id="60cc8-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="60cc8-112">Zulässige Werte sind UNC oder HTTP.</span><span class="sxs-lookup"><span data-stu-id="60cc8-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="60cc8-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="60cc8-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="60cc8-114">Die Anzahl an Millisekunden, die das Programm wartet, um einen Sound zu laden, bevor es eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="60cc8-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="60cc8-115">Der Standardwert ist 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="60cc8-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="60cc8-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="60cc8-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="60cc8-117">Ein boolescher Wert, der angibt, ob der Sound fertig geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="60cc8-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="60cc8-118"><xref:System.Media.SoundPlayer.Load%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="60cc8-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="60cc8-119">Lädt einen Sound synchron.</span><span class="sxs-lookup"><span data-stu-id="60cc8-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="60cc8-120"><xref:System.Media.SoundPlayer.LoadAsync%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="60cc8-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="60cc8-121">Fängt an, einen Sound asynchron zu laden.</span><span class="sxs-lookup"><span data-stu-id="60cc8-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="60cc8-122">Wenn der Ladevorgang abgeschlossen ist, löst die <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="60cc8-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="60cc8-123"><xref:System.Media.SoundPlayer.Play%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="60cc8-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="60cc8-124">Gibt den Sound angegeben wird, der <xref:System.Media.SoundPlayer.SoundLocation%2A> oder <xref:System.Media.SoundPlayer.Stream%2A> Eigenschaft in einem neuen Thread.</span><span class="sxs-lookup"><span data-stu-id="60cc8-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="60cc8-125"><xref:System.Media.SoundPlayer.PlaySync%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="60cc8-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="60cc8-126">Gibt den Sound angegeben wird, der <xref:System.Media.SoundPlayer.SoundLocation%2A> oder <xref:System.Media.SoundPlayer.Stream%2A> Eigenschaft im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="60cc8-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="60cc8-127"><xref:System.Media.SoundPlayer.Stop%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="60cc8-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="60cc8-128">Beendet den aktuell wiedergegebenen Sound.</span><span class="sxs-lookup"><span data-stu-id="60cc8-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="60cc8-129"><xref:System.Media.SoundPlayer.LoadCompleted>-Ereignis</span><span class="sxs-lookup"><span data-stu-id="60cc8-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="60cc8-130">Wird ausgelöst, nachdem versucht wurde, einen Sound zu laden.</span><span class="sxs-lookup"><span data-stu-id="60cc8-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60cc8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60cc8-131">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
