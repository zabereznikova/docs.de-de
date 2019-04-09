---
title: Windows Communication Foundation-Architektur
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], architecture
- WCF [WCF], architecture
- architecture [WCF]
ms.assetid: a3bcb0a1-56ea-4ba6-9736-d260d90dade5
ms.openlocfilehash: b0e4f9af0ff84a8d560b332d227b1ba9ae18bd4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099702"
---
# <a name="windows-communication-foundation-architecture"></a>Windows Communication Foundation-Architektur
Die folgende Abbildung veranschaulicht die Hauptebenen der Architektur von Windows Communication Foundation (WCF).  
  
## <a name="wcf-architecture"></a>WCF-Architektur  
 ![Der WCF-Architektur](../../../docs/framework/wcf/media/wcf-architecture.gif "WCF_Architecture")  
  
### <a name="contracts-and-descriptions"></a>Verträge und Beschreibungen  
 Verträge definieren verschiedene Aspekte des Nachrichtensystems. Der Datenvertrag beschreibt alle Parameter, aus denen die einzelnen Nachrichten bestehen, die ein Dienst erstellen oder verarbeiten kann. Die Nachrichtenparameter werden in XSD-Dokumenten (XML-Schemadefinitionssprache) definiert. Dadurch kann jedes XML-fähige System die Dokumente verarbeiten. Der Nachrichtenvertrag definiert anhand von SOAP-Protokollen bestimmte Nachrichtenteile und ermöglicht eine detailliertere Steuerung der Teile einer Nachricht, wenn die Interoperabilität diese Genauigkeit verlangt. Der Dienstvertrag gibt die tatsächlichen Methodensignaturen des Dienstes an und wird als Schnittstelle in einer der unterstützten Programmiersprachen verteilt (z.&amp;#160;B. Visual Basic oder Visual C#).  
  
 Richtlinien und Bindungen legen die zur Kommunikation mit einem Dienst erforderlichen Bedingungen fest.  Beispielsweise muss die Bindung (mindestens) den verwendeten Transport (z.&amp;#160;B. HTTP oder TCP) und eine Codierung angeben. Richtlinien schließen Sicherheitsanforderungen und andere Bedingungen ein, die für die Kommunikation mit einem Dienst erfüllt werden müssen.  
  
### <a name="service-runtime"></a>Dienstlaufzeit  
 Die Dienstlaufzeitebene umfasst Verhaltensweisen, die nur während der tatsächlichen Ausführung des Dienstes auftreten, d.&amp;#160;h. das Laufzeitverhalten des Dienstes. Die Drosselung steuert, wie viele Nachrichten verarbeitet werden. Diese Zahl kann geändert werden, wenn die Nachfrage nach dem Dienst ein voreingestelltes Limit erreicht. Für den Fall eines internen Dienstfehlers gibt das Fehlerverhalten die zu ergreifenden Maßnahmen an, z.&amp;#160;B. indem es steuert, welche Informationen an den Client übermittelt werden. (Zu viele Informationen könnten einem böswilligen Benutzer einen Angriff erleichtern.) Das Metadatenverhalten bestimmt, wie und ob Metadaten öffentlich verfügbar gemacht werden. Wie viele Instanzen des Dienstes ausgeführt werden können, wird vom Instanzenverhalten angegeben (Singleton gibt z. B. nur eine Instanz zur Verarbeitung aller Nachrichten an). Das Transaktionsverhalten ermöglicht einen Rollback von durchgeführten Vorgängen im Fall eines Fehlers. Verteilungsverhalten wird das Steuerelement wie eine Nachricht von der WCF-Infrastruktur verarbeitet wird.  
  
 Die Erweiterbarkeit ermöglicht eine Anpassung der Laufzeitprozesse. Beispielsweise werden mit der Nachrichteninspektion Teile einer Nachricht überprüft, und mit der Parameterfilterung finden anhand von Filtern, die auf Nachrichtenheader angewendet werden, voreingestellte Aktionen statt.  
  
### <a name="messaging"></a>Messaging  
 Die Messagingebene besteht aus *Kanäle*. Ein Kanal ist eine Komponete, die eine Nachricht in bestimmter Weise verarbeitet, z.&amp;#160;B. durch Authentifizierung. Eine Reihe von Kanälen wird auch eine *Kanalstapel*. Kanäle arbeiten mit Nachrichten und Nachrichtenheadern. Die Dienstlaufzeitebene hingegen verarbeitet hauptsächlich den Inhalt des Nachrichtentexts.  
  
 Es gibt zwei Arten von Kanälen: Transportkanäle und Protokollkanäle.  
  
 Transportkanäle lesen und schreiben Nachrichten aus dem Netzwerk (oder einem Kommunikationspunkt zur Außenwelt). Bei einigen Transporten wird ein Encoder verwendet, um Nachrichten (die als XML-Infosets dargestellt werden) in und aus der Bytestreamdarstellung des Netzwerks zu konvertieren. HTTP, benannte Pipes, TCP und MSMQ sind Beispiele für Transporte. Beispiele für Codierungen sind XML und optimierte Binärdateien.  
  
 Protokollkanäle implementieren Nachrichtenverarbeitungsprotokolle. Das erfolgt häufig durch Lesen oder Schreiben zusätzlicher Header in die Nachricht. Zu diesen Protokollen gehören beispielsweise WS-Security und WS-Reliability.  
  
 Die Messagingebene stellt die möglichen Formate und die Austauschmuster der Daten dar. WS-Security ist eine Implementierung der WS-Security-Spezifikation, die die Sicherheit auf der Nachrichtenebene aktiviert. Der WS-Reliable Messaging-Kanal stellt die Nachrichtenübermittlung sicher. Mit einer Vielzahl von Codierungen ermöglichen es Encoder, die Nachrichtenanforderungen zu erfüllen. Der HTTP-Kanal gibt die Verwendung des Hypertextübertragungsprotokolls zur Nachrichtenübermittlung an. Entsprechend gibt der TCP-Kanal die Verwendung des TCP-Protokolls an. Der Transaktionsflusskanal bestimmt die Muster von Transaktionsnachrichten. Der Kanal für benannte Pipes ermöglicht die prozessübergreifende Kommunikation. Der MSMQ-Kanal ermöglicht die Interoperation zwischen MSMQ-Anwendungen.  
  
### <a name="hosting-and-activation"></a>Hosting und Aktivierung  
 Ein Dienst ist letztendlich ein Programm. Wie andere Programme muss ein Dienst in einer ausführbaren Datei ausgeführt werden. Dies bezeichnet man als ein *selbstgehostet* Service.  
  
 Dienst kann auch wird *gehosteten*, oder führen Sie in eine ausführbare Datei, die von einem externen Agenten, z. B. IIS oder Windows-Prozessaktivierungsdienst (WAS) verwaltet werden. WCF-Anwendungen ermöglicht, automatisch aktiviert werden, bei der Bereitstellung auf einem Computer mit war. Sie können Dienste gegebenenfalls manuell als ausführbare Dateien (EXE-Dateien) ausführen. Ein Dienst kann auch automatisch als Windows-Dienst ausgeführt werden. COM+-Komponenten können auch als WCF-Dienste gehostet werden.  
  
## <a name="see-also"></a>Siehe auch

- [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)
- [Wesentliche Windows Communication Foundation-Begriffe](../../../docs/framework/wcf/fundamental-concepts.md)
