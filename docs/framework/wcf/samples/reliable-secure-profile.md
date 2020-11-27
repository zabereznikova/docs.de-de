---
title: Reliable Secure Profile
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
ms.openlocfilehash: 0647b8eaec39b990c139d970b5af1159fb18f8e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267233"
---
# <a name="reliable-secure-profile"></a>Reliable Secure Profile

In diesem Beispiel wird veranschaulicht, wie WCF und [zuverlässiges sicheres Profil (Secure Profile, RSP)](http://www.ws-i.org/Profiles/ReliableSecureProfile-1.0.html)verfasst werden. Dieses Beispiel veranschaulicht die Implementierung eines [make-Verbindungs](http://docs.oasis-open.org/ws-rx/wsmc/200702/wsmc-1.0-spec-cs-01.pdf) Kanals, der zusammen mit zuverlässigem Messaging und optional einem sicheren Kanal zum Erstellen einer zuverlässigen sicheren Bindung basierend auf der RSP-Spezifikation zusammengesetzt werden kann.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>Diskussion  

 In diesem Beispiel wird ein zuverlässiges asynchrones, bidirektionales Nachrichtenaustauschszenario veranschaulicht. Der Dienst verfügt über einen Duplexvertrag, und der Client implementiert den Duplexrückrufvertrag. Der Client initiiert eine Anforderung an einen Dienst, für den eine Antwort für eine separate Verbindung erwartet wird. Die Anforderungsmeldung wird zuverlässig gesendet. Der Client möchte selbst keinen überwachenden Endpunkt öffnen. Deshalb sendet er eine Abfrage an den Dienst mit 'Make Connection'-Anforderungen, damit die Antwort auf dem Rückkanal dieser 'Make Connection'-Anforderung zurückgesendet werden soll. In diesem Beispiel wird veranschaulicht die sichere zuverlässige Duplexkommunikation über HTTP, ohne dass der Client einen überwachenden Endpunkt verfügbar machen muss oder eine Firewallausnahme erstellt werden soll.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Öffnen Sie die Projekt Mappe **reliablesecureprofile** .  
  
2. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **Debuggen** und dann **neue Instanz starten** aus. Daraufhin wird der Diensthost gestartet.  
  
3. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das **Client** Projekt, wählen Sie **Debuggen**, **neue Instanz starten** aus dem Kontextmenü. Daraufhin wird der Client gestartet.  
  
4. Geben Sie eine beliebige Zeichenfolge in die Eingabeaufforderung im Clientkonsolenfenster ein, und drücken Sie die EINGABETASTE. Daraufhin wird die Eingabezeichenfolge an den Dienst gesendet, und dieser berechnet einen Hash der Zeichenfolge.  
  
5. Zeigen Sie das Ergebnis in den Clientfenstern an, wenn der Vorgang mit dem Duplexrückrufvertrag vom Dienst zurückgerufen wird, um das Ergebnis im Clientkonsolenfenster anzuzeigen. Es gibt eine absichtliche Verzögerung im Dienst, um einen lange andauernden Ausführungsvorgang zur Datenverarbeitung zu simulieren.  
  
6. Die Überwachung des HTTP-Datenverkehrs (durch ein Online-Netzwerküberwachungstool wie Network Monitor, Fiddler usw.) zeigt an, dass eine Sequenz für die Kommunikation zwischen dem Client und dem Dienst gemäß dem Vorbild des Reliable Secure Profile erstellt wird, und demonstriert, wie der Client 'Make Connection'-Anforderungen als Abfragen an den Dienst sendet. Wenn der Dienst sich darauf vorbereitet, die die verarbeitete Antwort zurückzusenden, sendet es die Ergebnisse über den Rückkanal der letzten 'Make Connection'-Anforderung zurück.  
  
7. Drücken Sie im Dienstkonsolenfenster die EINGABETASTE, um den Dienst zu schließen. Drücken Sie im Clientkonsolenfenster die EINGABETASTE, um den Client zu schließen.
