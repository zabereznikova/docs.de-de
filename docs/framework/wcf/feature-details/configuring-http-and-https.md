---
title: Konfigurieren von HTTP und HTTPS
ms.date: 04/08/2019
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: f7fd2bad6ced09b638cc1bb5d539fab1b9ce7d25
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75336700"
---
# <a name="configuring-http-and-https"></a>Konfigurieren von HTTP und HTTPS

WCF-Dienste und -Clients können über HTTP und HTTPS kommunizieren. Die HTTP/HTTPS-Einstellungen werden mit Internetinformationsdienste (IIS) oder mit einem Befehlszeilentool konfiguriert. Wenn ein WCF-Dienst unter IIS gehostet wird, können die HTTP- oder HTTPS-Einstellungen in IIS konfiguriert werden (mit dem Tool "inetmgr.exe"). Bei einem selbst gehosteten WCF-Dienst werden die HTTP- oder HTTPS-Einstellungen mit einem Befehlszeilentool konfiguriert.

Sie möchten mindestens eine URL-Registrierung konfigurieren und eine Firewallausnahme für die URL hinzufügen, die der Dienst verwendet. Sie können diese Einstellungen mit dem Tool "Netsh. exe" konfigurieren.

## <a name="configuring-namespace-reservations"></a>Konfigurieren von Namespace Reservierungen

Eine Namespacereservierung weist die Rechte für einen Teil des HTTP-URL-Namespace einer bestimmten Gruppe von Benutzern zu. Eine Reservierung erteilt diesen Benutzern die Berechtigung zum Erstellen von Diensten, die diesen Teil des Namespace überwachen. Reservierungen sind URL-Präfixe, d. h., die Reservierung deckt alle unter Pfade des Reservierungs Pfads ab. Namespacereservierungen eröffnen zwei Möglichkeiten, Platzhalter zu verwenden. In der HTTP-Server-API-Dokumentation wird die [Reihenfolge der Auflösung zwischen Namespace Ansprüchen, die Platzhalter einschließen,](/windows/desktop/Http/routing-incoming-requests)beschrieben.

Eine laufende Anwendung kann eine ähnliche Anforderung stellen, um Namespaceregistrierungen hinzuzufügen. Registrierungen und Reservierungen konkurrieren um Teile des Namespaces. Eine Reservierung hat möglicherweise Vorrang vor einer Registrierung entsprechend der Auflösungs Reihenfolge in der [Reihenfolge der Auflösung zwischen Namespace Ansprüchen, die](/windows/desktop/Http/routing-incoming-requests)Platzhalter einschließen. In diesem Fall blockiert die Reservierung in der laufenden Anwendung den Empfang von Anforderungen.

Im folgenden Beispiel wird das Tool Netsh. exe verwendet:

```console
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user
```

Mit diesem Befehl wird eine URL-Reservierung für den angegebenen URL-Namespace für das Konto "Domäne \ Benutzer" hinzugefügt. Weitere Informationen zur Verwendung des Netsh-Befehls erhalten Sie, indem Sie in einer Eingabeaufforderung `netsh http add urlacl /?` eingeben und die EINGABETASTE drücken.

## <a name="configuring-a-firewall-exception"></a>Konfigurieren einer Firewallausnahme

Beim Selbsthosting eines WCF-Diensts, der über HTTP kommuniziert, muss der Firewallkonfiguration eine Ausnahme hinzugefügt werden, die eingehende Verbindungen über eine bestimmte URL zulässt.

## <a name="configuring-ssl-certificates"></a>Konfigurieren von SSL-Zertifikaten

Das Secure Sockets Layer (SSL)-Protokoll verwendet Zertifikate auf Client und Server, um Verschlüsselungsschlüssel zu speichern. Der Server muss ein SSL-Zertifikat bereitstellen, wenn eine Verbindung hergestellt wird, damit der Client die Identität des Servers überprüfen kann. Der Server kann ebenfalls ein Zertifikat vom Client anfordern, so dass eine wechselseitige Authentifizierung auf beiden Seiten der Verbindung möglich wird.

Zertifikate sind in einem zentralen Speicher entsprechend der IP-Adresse und der Anschlussnummer der Verbindung gespeichert. Die spezielle IP-Adresse 0.0.0.0 stimmt mit jeder IP-Adresse für den lokalen Computer überein. Beachten Sie, dass der Zertifikat Speicher keine URLs basierend auf dem Pfad unterscheidet. Dienste mit der gleichen Kombination von IP-Adresse und Anschlussnummer müssen die gleichen Zertifikate verwenden, auch wenn sich der Pfad in der URL dieser Dienste unterscheidet.

Schritt-für-Schritt-Anweisungen finden Sie unter Vorgehens [Weise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).

## <a name="configuring-the-ip-listen-list"></a>Konfigurieren der IP-Lauschliste

Die HTTP-Server-API stellt erst dann eine Bindung mit einer IP-Adresse und einem Port her, wenn ein Benutzer eine URL registriert. Standardmäßig verbindet die HTTP-Server-API mit dem Anschluss in der URL für alle IP-Adressen des Computers. Ein Konflikt tritt auf, wenn eine Anwendung, die die HTTP-Server-API nicht verwendet, zuvor an diese Kombination von IP-Adresse und Port gebunden ist. Die IP-Abhörliste ermöglicht die Koexistenz von WCF-Diensten mit Anwendungen, die einen Port für einige der IP-Adressen des Computers verwenden. Enthält die IP-Lauschliste irgendwelche Einträge, verbindet die HTTP-Server-API nur mit den IP-Adressen, die in der Liste angegeben sind. Die Änderung der IP-Lauschliste erfordert Administratorrechte.

Verwenden Sie das Tool Netsh, um die IP-lausch Liste zu ändern, wie im folgenden Beispiel gezeigt:

```console
netsh http add iplisten ipaddress=0.0.0.0:8000
```

## <a name="other-configuration-settings"></a>Weitere Konfigurationseinstellungen

Bei Verwendung der <xref:System.ServiceModel.WSDualHttpBinding> verwendet die Clientverbindung Standardwerte, die mit Namespacereservierungen und der Windows-Firewall kompatibel sind. Wenn Sie sich dafür entscheiden, die Clientbasisadresse einer dualen Verbindung anzupassen, müssen Sie diese HTTP-Einstellungen auch auf dem Client mit der neuen Adresse konfigurieren.

Die HTTP-Server-API verfügt über einige erweiterte Konfigurationseinstellungen, die über Httpcfg nicht verfügbar sind. Diese Einstellungen sind in der Registrierung gespeichert und gelten für alle Anwendungen, die auf Systemen laufen, die HTTP-Server-APIs verwenden. Weitere Informationen zu diesen Einstellungen finden Sie unter [http. sys-Registrierungs Einstellungen für IIS](https://support.microsoft.com/help/820129/http-sys-registry-settings-for-windows). Die meisten Benutzer müssen diese Einstellungen nicht ändern.

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.WSDualHttpBinding>
- [Vorgehensweise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md)
