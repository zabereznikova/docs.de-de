---
title: "Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource | Microsoft Docs"
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
  - "Zeitzonen [.NET Framework], Deserialisieren"
  - "Zeitzonen [.NET Framework], Wiederherstellen"
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource
In diesem Thema wird beschrieben, wie in einer Ressourcendatei gespeicherte Zeitzonen wiederhergestellt werden.  Informationen und Anweisungen zum Speichern von Zeitzonen finden Sie unter [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).  
  
### So deserialisieren Sie ein TimeZoneInfo\-Objekt aus einer eingebetteten Ressource  
  
1.  Wenn es sich bei der abzurufenden Zeitzone nicht um eine benutzerdefinierte Zeitzone handelt, versuchen Sie, diese mit der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>\-Methode zu instanziieren.  
  
2.  Instanziieren Sie ein <xref:System.Resources.ResourceManager>\-Objekt, indem Sie den vollqualifizierten Namen der eingebetteten Ressourcendatei und einen Verweis auf die Assembly, in der die Ressourcendatei enthalten ist, übergeben.  
  
     Wenn Sie den vollqualifizierten Namen der eingebetteten Ressourcendatei nicht ermitteln können, verwenden Sie den [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) zum Untersuchen des Assemblymanifests.  Die Ressource wird durch einen `.mresource`\-Eintrag identifiziert.  Im Beispiel lautet der vollqualifizierte Name der Ressource `SerializeTimeZoneData.SerializedTimeZones`.  
  
     Wenn die Ressourcendatei in die gleiche Assembly eingebettet ist, die auch den Code zum Instanziieren der Zeitzone beinhaltet, können Sie einen Verweis darauf abrufen, indem Sie die `static` \(`Shared` in Visual Basic\) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>\-Methode aufrufen.  
  
3.  Wenn der Aufruf der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>\-Methode nicht erfolgreich ist oder wenn eine benutzerdefinierte Zeitzone instanziiert werden soll, rufen Sie eine Zeichenfolge mit der serialisierten Zeitzone ab, indem Sie die <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>\-Methode aufrufen.  
  
4.  Deserialisieren Sie die Zeitzonendaten, indem Sie die <xref:System.TimeZoneInfo.FromSerializedString%2A>\-Methode aufrufen.  
  
## Beispiel  
 Im folgenden Beispiel wird ein in einer eingebetteten .NET\-XML\-Ressourcendatei gespeichertes <xref:System.TimeZoneInfo>\-Objekt deserialisiert.  
  
 [!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
 [!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]  
  
 Dieser Code veranschaulicht die Ausnahmebehandlung, mit der sichergestellt wird, dass ein für die Anwendung erforderliches <xref:System.TimeZoneInfo>\-Objekt vorhanden ist.  Es wird zunächst versucht, ein <xref:System.TimeZoneInfo>\-Objekt durch Abrufen aus der Registrierung mithilfe der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>\-Methode zu instanziieren.  Wenn die Zeitzone nicht instanziiert werden kann, ruft der Code sie aus der eingebetteten Ressourcendatei ab.  
  
 Da Daten benutzerdefinierter Zeitzonen \(mit der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode instanziierte Zeitzonen\) nicht in der Registrierung gespeichert werden, ruft der Code nicht <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> auf, um die Zeitzone für Palmer, Antarktis zu instanziieren.  Stattdessen wird versucht, eine Zeichenfolge mit den Zeitzonendaten direkt aus der eingebetteten Ressourcendatei abzurufen, bevor die <xref:System.TimeZoneInfo.FromSerializedString%2A>\-Methode aufgerufen wird.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Verweis auf System.Windows.Forms.dll und System.Core.dll muss dem Projekt hinzugefügt werden.  
  
-   Die folgenden Namespaces müssen importiert werden:  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)   
 [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)