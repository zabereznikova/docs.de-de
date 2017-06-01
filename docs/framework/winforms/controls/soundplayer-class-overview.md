---
title: "&#220;bersicht &#252;ber die SoundPlayer-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Wiedergabe von Tönen SoundPlayer-Klasse"
  - "SoundPlayer-Klasse Informationen über die SoundPlayer-Klasse"
  - "Wiedergabe von Sounds"
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber die SoundPlayer-Klasse
Die <xref:System.Media.SoundPlayer> -Klasse ermöglicht es Ihnen, Sounds problemlos in Ihre Anwendung integrieren.  
  
 Die <xref:System.Media.SoundPlayer> -Klasse Audiodateien im WAV-Format aus einer Ressource oder aus UNC oder HTTP-Speicherorte wiedergeben kann. Darüber hinaus die <xref:System.Media.SoundPlayer> -Klasse ermöglicht es Ihnen zu laden oder Sound asynchron.  
  
 Sie können auch die <xref:System.Media.SystemSounds> Klasse, um allgemeine Systemsounds wiederzugeben, einschließlich eines akustischen Signals.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Am häufigsten verwendeten Eigenschaften, Methoden und Ereignisse  
  
|Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> Eigenschaft|Der Dateipfad oder die Webadresse des Sounds. Die zulässigen Werte möglich UNC oder HTTP.|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> Eigenschaft|Die Anzahl der Millisekunden, die das Programm wartet auf einen Sound vor dem Laden eine Ausnahme auslöst. Der Standardwert ist 10 Sekunden.|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> Eigenschaft|Ein boolescher Wert, der angibt, ob der Sound vollständig geladen wurde.|  
|<xref:System.Media.SoundPlayer.Load%2A> Methode|Lädt einen Sound synchron aus.|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> Methode|Zum asynchronen Laden eines Sounds beginnt. Wenn der Ladevorgang abgeschlossen ist, löst es das <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> Ereignis.|  
|<xref:System.Media.SoundPlayer.Play%2A> Methode|Gibt den Sound gemäß der <xref:System.Media.SoundPlayer.SoundLocation%2A> oder <xref:System.Media.SoundPlayer.Stream%2A> Eigenschaft in einem neuen Thread.|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> Methode|Gibt den Sound gemäß der <xref:System.Media.SoundPlayer.SoundLocation%2A> oder <xref:System.Media.SoundPlayer.Stream%2A> Eigenschaft im aktuellen Thread.|  
|<xref:System.Media.SoundPlayer.Stop%2A> Methode|Wird alle aktuell wiedergegebenen Sounds beendet.|  
|<xref:System.Media.SoundPlayer.LoadCompleted> Ereignis|Wird ausgelöst, nachdem das Laden eines Sounds versucht wird.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>