---
title: Windows Communication Foundation-Architektur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], architecture
- WCF [WCF], architecture
- architecture [WCF]
ms.assetid: a3bcb0a1-56ea-4ba6-9736-d260d90dade5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bc7383c5b93203b144c965f06fa7365c864de27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-architecture"></a>Windows Communication Foundation-Architektur
Die folgende Darstellung veranschaulicht die Hauptebenen der Architektur von [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="wcf-architecture"></a>WCF-Architektur  
 ![Die WCF-Architektur](../../../docs/framework/wcf/media/wcf-architecture.gif "WCF_Architecture")  
  
### <a name="contracts-and-descriptions"></a>Verträge und Beschreibungen  
 Verträge definieren verschiedene Aspekte des Nachrichtensystems. Der Datenvertrag beschreibt alle Parameter, aus denen die einzelnen Nachrichten bestehen, die ein Dienst erstellen oder verarbeiten kann. Die Nachrichtenparameter werden in XSD-Dokumenten (XML-Schemadefinitionssprache) definiert. Dadurch kann jedes XML-fähige System die Dokumente verarbeiten. Der Nachrichtenvertrag definiert anhand von SOAP-Protokollen bestimmte Nachrichtenteile und ermöglicht eine detailliertere Steuerung der Teile einer Nachricht, wenn die Interoperabilität diese Genauigkeit verlangt. Der Dienstvertrag gibt die tatsächlichen Methodensignaturen des Dienstes an und wird als Schnittstelle in einer der unterstützten Programmiersprachen verteilt (z.&#160;B. Visual Basic oder Visual C#).  
  
 Richtlinien und Bindungen legen die zur Kommunikation mit einem Dienst erforderlichen Bedingungen fest.  Beispielsweise muss die Bindung (mindestens) den verwendeten Transport (z.&#160;B. HTTP oder TCP) und eine Codierung angeben. Richtlinien schließen Sicherheitsanforderungen und andere Bedingungen ein, die für die Kommunikation mit einem Dienst erfüllt werden müssen.  
  
### <a name="service-runtime"></a>Dienstlaufzeit  
 Die Dienstlaufzeitebene umfasst Verhaltensweisen, die nur während der tatsächlichen Ausführung des Dienstes auftreten, d.&#160;h. das Laufzeitverhalten des Dienstes. Die Drosselung steuert, wie viele Nachrichten verarbeitet werden. Diese Zahl kann geändert werden, wenn die Nachfrage nach dem Dienst ein voreingestelltes Limit erreicht. Für den Fall eines internen Dienstfehlers gibt das Fehlerverhalten die zu ergreifenden Maßnahmen an, z.&#160;B. indem es steuert, welche Informationen an den Client übermittelt werden. (Zu viele Informationen könnten einem böswilligen Benutzer einen Angriff erleichtern.) Das Metadatenverhalten bestimmt, wie und ob Metadaten öffentlich verfügbar gemacht werden. Wie viele Instanzen des Dienstes ausgeführt werden können, wird vom Instanzenverhalten angegeben (Singleton gibt z. B. nur eine Instanz zur Verarbeitung aller Nachrichten an). Das Transaktionsverhalten ermöglicht einen Rollback von durchgeführten Vorgängen im Fall eines Fehlers. Mit dem Verteilungsverhalten wird die Verarbeitung von Nachrichten durch die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Infrastruktur gesteuert.  
  
 Die Erweiterbarkeit ermöglicht eine Anpassung der Laufzeitprozesse. Beispielsweise werden mit der Nachrichteninspektion Teile einer Nachricht überprüft, und mit der Parameterfilterung finden anhand von Filtern, die auf Nachrichtenheader angewendet werden, voreingestellte Aktionen statt.  
  
### <a name="messaging"></a>Messaging  
 Die Messagingebene besteht *Kanäle*. Ein Kanal ist eine Komponete, die eine Nachricht in bestimmter Weise verarbeitet, z.&#160;B. durch Authentifizierung. Ein Satz von Kanälen ist auch bekannt als ein *Kanalstapel*. Kanäle arbeiten mit Nachrichten und Nachrichtenheadern. Die Dienstlaufzeitebene hingegen verarbeitet hauptsächlich den Inhalt des Nachrichtentexts.  
  
 Es gibt zwei Arten von Kanälen: Transportkanäle und Protokollkanäle.  
  
 Transportkanäle lesen und schreiben Nachrichten aus dem Netzwerk (oder einem Kommunikationspunkt zur Außenwelt). Bei einigen Transporten wird ein Encoder verwendet, um Nachrichten (die als XML-Infosets dargestellt werden) in und aus der Bytestreamdarstellung des Netzwerks zu konvertieren. HTTP, benannte Pipes, TCP und MSMQ sind Beispiele für Transporte. Beispiele für Codierungen sind XML und optimierte Binärdateien.  
  
 Protokollkanäle implementieren Nachrichtenverarbeitungsprotokolle. Das erfolgt häufig durch Lesen oder Schreiben zusätzlicher Header in die Nachricht. Zu diesen Protokollen gehören beispielsweise WS-Security und WS-Reliability.  
  
 Die Messagingebene stellt die möglichen Formate und die Austauschmuster der Daten dar. WS-Security ist eine Implementierung der WS-Security-Spezifikation, die die Sicherheit auf der Nachrichtenebene aktiviert. Der WS-Reliable Messaging-Kanal stellt die Nachrichtenübermittlung sicher. Mit einer Vielzahl von Codierungen ermöglichen es Encoder, die Nachrichtenanforderungen zu erfüllen. Der HTTP-Kanal gibt die Verwendung des Hypertextübertragungsprotokolls zur Nachrichtenübermittlung an. Entsprechend gibt der TCP-Kanal die Verwendung des TCP-Protokolls an. Der Transaktionsflusskanal bestimmt die Muster von Transaktionsnachrichten. Der Kanal für benannte Pipes ermöglicht die prozessübergreifende Kommunikation. Der MSMQ-Kanal ermöglicht die Interoperation zwischen MSMQ-Anwendungen.  
  
### <a name="hosting-and-activation"></a>Hosting und Aktivierung  
 Ein Dienst ist letztendlich ein Programm. Wie andere Programme muss ein Dienst in einer ausführbaren Datei ausgeführt werden. Dies bezeichnet man eine *selbstgehosteten* Dienst.  
  
 Dienste können auch sein *gehostet*, oder führen Sie in einer ausführbaren Datei von einem externen Agenten, z. B. IIS oder Windows Activation Service (WAS) verwaltet werden. WAS ermöglicht es, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Anwendungen auf Computern, auf denen WAS ausgeführt wird, automatisch zu aktivieren. Sie können Dienste gegebenenfalls manuell als ausführbare Dateien (EXE-Dateien) ausführen. Ein Dienst kann auch automatisch als Windows-Dienst ausgeführt werden. Auch COM+-Komponenten können als [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienste gehostet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Wesentliche Windows Communication Foundation-Begriffe](../../../docs/framework/wcf/fundamental-concepts.md)
