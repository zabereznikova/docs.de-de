---
title: Änderungen an der NTLM-Authentifizierung für „HttpWebRequest“ in Version 3.5 SP1
ms.date: 03/30/2017
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
ms.openlocfilehash: 388e6dc648e1fd68e24a852cb08de107f09f9c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "64754877"
---
# <a name="changes-to-ntlm-authentication-for-httpwebrequest-in-version-35-sp1"></a>Änderungen an der NTLM-Authentifizierung für „HttpWebRequest“ in Version 3.5 SP1

Es wurden Sicherheitsänderungen in .NET Framework Version 3.5 SP1 und höher vorgenommen, die beeinflussen, wie die integrierte Windows-Authentifizierung durch <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Security.NegotiateStream> und verwandte Klassen im System.Net-Namespace behandelt wird. Diese Änderungen können sich auf Anwendungen auswirken, die diese Klassen für Webanforderungen und den Empfang der Antworten verwenden, in denen die integrierte Windows-Authentifizierung auf NTLM-Basis verwendet wird. Die Änderung kann sich auf Webserver und Clientanwendungen auswirken, die für die Verwendung der integrierten Windows-Authentifizierung konfiguriert sind.

## <a name="overview"></a>Übersicht

Durch die Gestaltung der integrierten Windows-Authentifizierung sind einige Abfragerückmeldungen zu Anmeldeinformationen universell, d.h., sie können wiederverwendet oder weitergeleitet werden. Wenn diese bestimmte Entwurfsfunktion nicht erforderlich ist, müssen die Authentifizierungsprotokolle zielspezifische Informationen sowie bestimmte Kanalinformationen enthalten. Der erweiterte Schutz kann dann von Diensten bereitgestellt werden, damit Abfragerückmeldungen zu Anmeldeinformationen auch sicher dienstspezifische Informationen, wie z.B. einen Dienstprinzipalnamen (SPN), enthalten. Enthält der Austausch von Anmeldedaten diese Informationen, können die Dienste besser vor einer böswilligen Verwendung von Abfragerückmeldungen geschützt werden, die möglicherweise nicht ordnungsgemäß verwendet wurden.

Mehrere Komponenten der Namespaces <xref:System.Net> und <xref:System.Net.Security> führen die integrierte Windows-Authentifizierung für eine aufrufende Anwendung aus. In diesem Abschnitt werden die erforderlichen Änderungen an System.Net-Komponenten beschrieben, um den erweiterten Schutz ihrer Verwendung der integrierten Windows-Authentifizierung hinzuzufügen.

## <a name="changes"></a>Änderungen

Der bei der integrierten Windows-Authentifizierung verwendete NTLM-Authentifizierungsvorgang enthält eine Abfrage, die vom Zielcomputer ausgegeben und an den Clientcomputer zurückgesendet wird. Wenn ein Computer eine Abfrage erhält, die er selbst generiert hat, schlägt die Authentifizierung fehl, es sei denn, es handelt sich um eine Schleife (z.B. IPv4-Adresse 127.0.0.1).

Beim Zugriff auf einen Dienst, der auf einem internen Webserver ausgeführt wird, ist es üblich, mithilfe einer URL ähnlich wie `http://contoso/service` oder `https://contoso/service` auf den Dienst zuzugreifen. Der Name „Contoso“ ist häufig nicht der Computername des Computers, auf dem der Dienst bereitgestellt wird. Die <xref:System.Net> und zugehörigen Namespaces unterstützen, mithilfe von Active Directory, DNS, NetBIOS, die Hostdatei des lokalen Computers (in der Regel beispielsweise WINDOWS\system32\drivers\etc\hosts) oder die die LmHostdatei des lokalen Computers (in der Regel beispielsweise WINDOWS\system32\drivers\etc\lmhosts) zum Auflösen von Namen zu Adressen. Der Name „Contoso“ wird aufgelöst, sodass an „Contoso“ gesendete Anforderungen an den entsprechenden Servercomputer gesendet werden.

Bei der Konfiguration für große Bereitstellungen erhält die Bereitstellung mit dem zugrunde liegenden Computernamen, die nie von Clientanwendungen und Endbenutzern verwendet werden, in der Regel einen einzelnen virtuellen Servernamen. Sie können den Server z.B. `www.contoso.com` nennen, jedoch in einem internen Netzwerk einfach „Contoso“ verwenden. Dieser Name ist der Hostheader in der Clientwebanforderung. Das Feld „Host-Anforderungsheader“ gibt gemäß dem HTTP-Protokoll den Internet-Host und die Portanzahl der angeforderten Ressource an. Diese Information wird aus dem ursprünglichen URI abgerufen, der vom Benutzer oder der Referenzressource (in der Regel eine HTTP-URL) angegeben wird. Auf .NET Framework, Version 4, können diese Informationen auch vom Client mit der neuen <xref:System.Net.HttpWebRequest.Host%2A>-Eigenschaft festgelegt werden.

Die <xref:System.Net.AuthenticationManager>-Klasse steuert die verwalteten Authentifizierungskomponenten („Module“), die von abgeleiteten <xref:System.Net.WebRequest>-und den <xref:System.Net.WebClient>-Klassen verwendet werden. Die <xref:System.Net.AuthenticationManager>-Klasse enthält eine Eigenschaft, die ein <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=nameWithType>-Objekt verfügbar macht, das von einer URI-Zeichenfolge indiziert ist, damit Anwendungen eine benutzerdefinierte SPN-Zeichenfolge bereitstellen können, die während der Authentifizierung verwendet wird.

Version 3.5 SP1 gibt jetzt standardmäßig den Hostnamen in der Anforderungs-URL in der SPN im NTLM-Authentifizierungsaustausch (NT LAN Manager) an, wenn die <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A>-Eigenschaft nicht festgelegt ist. Der Hostname in der Anforderungs-URL kann vom in <xref:System.Net.HttpRequestHeader?displayProperty=nameWithType> in der Clientanforderung angegebenen Hostheader abweichen. Der Hostname in der Anforderungs-URL kann vom tatsächlichen Hostnamen des Servers, dem Computernamen des Servers, der IP-Adresse des Computers oder der Loopbackadresse abweichen. In diesen Fällen schlägt die Authentifizierungsanforderung in Windows fehl. Um das Problem zu beheben, müssen wir Windows benachrichtigen, dass der Hostname in der Anforderungs-URL in der Client-Anforderung (z.B. „Contoso“) tatsächlich ein alternativer Name für den lokalen Computer ist.

Es gibt mehrere Methoden, mit denen eine Serveranwendung diese Änderung umgehen kann. Die empfohlene Vorgehensweise ist, den Hostnamen in der Anforderungs-URL zum `BackConnectionHostNames`-Schlüssel in der Registrierung auf dem Server zuzuordnen. Der `BackConnectionHostNames`-Registrierungsschlüssel wird normalerweise verwendet, um einen Hostnamen einer Loopbackadresse zuzuordnen. Die Schritte sind unten aufgeführt.

Um die Hostnamen anzugeben, die der Loopbackadresse zugeordnet sind, und die mit Websites auf einem lokalen Computer verbunden werden können, gehen Sie folgendermaßen vor:

1. Klicken Sie auf „Start“ und auf „Ausführen“, geben Sie „regedit“ ein, und klicken Sie anschließend auf „OK“.

2. Suchen Sie im Registrierungs-Editor den folgenden Registrierungsschlüssel, und klicken Sie darauf:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`

3. Klicken Sie mit der rechten Maustaste auf „MSV1_0“, zeigen Sie auf „Neu“, und klicken Sie dann auf „Mehrteilige Zeichenfolge“.

4. Geben Sie `BackConnectionHostNames` ein, und drücken Sie dann die EINGABETASTE.

5. Klicken Sie mit der rechten Maustaste auf `BackConnectionHostNames`, und klicken Sie dann auf „Bearbeiten“.

6. Geben Sie im Feld „Wertdaten“ den Hostnamen oder die Hostnamen für die Standorte an (Hostname, der im Anforderungs-URL verwendet wird), die sich auf dem lokalen Computer befinden, und klicken Sie dann auf „OK“.

7. Beenden Sie den Registrierungs-Editor, starten Sie den IISAdmin-Dienst neu, und führen Sie IISReset aus.

Eine unsicherere Lösung ist die Deaktivierung der Loopbacküberprüfung, die in <https://support.microsoft.com/kb/896861> beschrieben ist. Der Schutz vor Reflektionsangriffen wird somit deaktiviert. Daher ist es besser, den Satz von alternativen Namen auf jene einzuschränken, von denen Sie erwarten, dass sie tatsächlich vom Computer verwendet werden.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=nameWithType>
- <xref:System.Net.HttpRequestHeader?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=nameWithType>
