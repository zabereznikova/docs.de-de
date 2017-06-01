---
title: "Suchen der auf einem lokalen System definierten Zeitzonen | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zugriff auf lokale Zeitzone"
  - "Zeitzonenbezeichner [.NET Framework]"
  - "Zeitzonen [.NET Framework], Suchen lokaler Systemzeitzonen"
  - "Zeitzonen [.NET Framework], Lokal"
  - "Zeitzonen [.NET Framework], Abrufen"
  - "Zeitzonen [.NET Framework], UTC"
  - "UTC-Zeiten, Suchen lokaler Systemzeitzonen"
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Suchen der auf einem lokalen System definierten Zeitzonen
Die <xref:System.TimeZoneInfo>\-Klasse macht keinen öffentlichen Konstruktor verfügbar.  Demzufolge kann das `new`\-Schlüsselwort nicht zum Erstellen eines neuen <xref:System.TimeZoneInfo>\-Objekts verwendet werden.  Stattdessen werden <xref:System.TimeZoneInfo>\-Objekte entweder durch Abrufen von Informationen über vordefinierte Zeitzonen aus der Registrierung oder durch Erstellen einer benutzerdefinierten Zeitzone instanziiert.  Dieses Thema behandelt die Instanziierung einer Zeitzone von den in der Registrierung gespeicherten Daten.  Darüber hinaus ermöglichen die `static`\-Eigenschaften \(`shared` in Visual Basic\) der <xref:System.TimeZoneInfo>\-Klasse Zugriff auf die koordinierte Weltzeit \(Universal Coordinated Time, UTC\) und die lokale Zeitzone.  
  
> [!NOTE]
>  Für Zeitzonen, die nicht in der Registrierung definiert sind, können Sie benutzerdefinierte Zeitzonen durch Aufrufen der Überladungen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode erstellen.  Das Erstellen einer benutzerdefinierten Zeitzone wird in den folgenden Themen erläutert: [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  Darüber hinaus können Sie ein <xref:System.TimeZoneInfo>\-Objekt durch Wiederherstellen aus einer serialisierten Zeichenfolge mit der <xref:System.TimeZoneInfo.FromSerializedString%2A>\-Methode instanziieren.  Das Serialisieren und Deserialisieren eines <xref:System.TimeZoneInfo>\-Objekts wird in den folgenden Themen erläutert: [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
## Zugreifen auf einzelne Zeitzonen  
 Die <xref:System.TimeZoneInfo>\-Klasse bietet zwei vordefinierte Zeitzonenobjekte, die die koordinierte Weltzeit und die lokale Zeitzone darstellen.  Diese werden jeweils über die <xref:System.TimeZoneInfo.Utc%2A>\- und die <xref:System.TimeZoneInfo.Local%2A>\-Eigenschaft zur Verfügung gestellt.  Anweisungen zum Zugreifen auf die UTC\-Zeit oder die lokalen Zeitzonen finden Sie unter [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md).  
  
 Sie können auch ein <xref:System.TimeZoneInfo>\-Objekt instanziieren, das die in der Registrierung definierten Zeitzonen darstellt.  Anweisungen zum Instanziieren eines bestimmten Zeitzonenobjekts finden Sie unter [Gewusst wie: Instanziieren eines TimeZoneInfo\-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md).  
  
## Zeitzonenbezeichner  
 Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert.  Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang.  In den meisten Fällen entspricht der dazugehörige Wert der <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=fullName>\-Eigenschaft, die zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird.  Es gibt jedoch auch Ausnahmen.  Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die dazugehörigen IDs zur Kenntnis zu nehmen.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md)   
 [Gewusst wie: Instanziieren eines TimeZoneInfo\-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)   
 [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md)