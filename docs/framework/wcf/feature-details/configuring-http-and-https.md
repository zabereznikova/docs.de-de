---
title: Konfigurieren von HTTP und HTTPS - WCF
ms.date: 04/08/2019
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: 86705a4f8daa327c442ac6c53c9b44c5b5c5c2ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857362"
---
# <a name="configuring-http-and-https"></a>Konfigurieren von HTTP und HTTPS

WCF-Dienste und -Clients können über HTTP und HTTPS kommunizieren. Die HTTP/HTTPS-Einstellungen werden mit Internetinformationsdienste (IIS) oder mit einem Befehlszeilentool konfiguriert. Wenn ein WCF-Dienst unter IIS gehostet wird, können die HTTP- oder HTTPS-Einstellungen in IIS konfiguriert werden (mit dem Tool "inetmgr.exe"). Bei einem selbst gehosteten WCF-Dienst werden die HTTP- oder HTTPS-Einstellungen mit einem Befehlszeilentool konfiguriert.

Mindestens möchten Sie eine URL-Registrierung konfigurieren, und fügen eine Firewallausnahme für die URL, die Ihrem Dienst verwendet wird. Sie können diese Einstellungen konfigurieren, mit dem Netsh.exe-Tool.

## <a name="configuring-namespace-reservations"></a>Konfigurieren von Namespacereservierungen

Eine Namespacereservierung weist die Rechte für einen Teil des HTTP-URL-Namespace einer bestimmten Gruppe von Benutzern zu. Eine Reservierung gibt diesen Benutzern das Recht, Dienste zu erstellen, die bei diesem Teil des Namespaces lauschen. Reservierungen sind URL-Präfixe, was bedeutet, dass die Reservierung auf alle Pfade reservierungspfad behandelt. Namespacereservierungen eröffnen zwei Möglichkeiten, Platzhalter zu verwenden. Die HTTP-Server-API-Dokumentation beschreibt die [Auflösungsreihenfolge von Namespace-Ansprüche, die Platzhalter verwenden](/windows/desktop/Http/routing-incoming-requests).

Eine laufende Anwendung kann eine ähnliche Anforderung stellen, um Namespaceregistrierungen hinzuzufügen. Registrierungen und Reservierungen konkurrieren um Teile des Namespaces. Eine Reservierung kann haben Vorrang vor einer Registrierung entsprechend der Auflösungsreihenfolge die [Auflösungsreihenfolge von Namespace-Ansprüche, die Platzhalter verwenden](/windows/desktop/Http/routing-incoming-requests). In diesem Fall blockiert die Reservierung in der laufenden Anwendung den Empfang von Anforderungen.

Im folgenden Beispiel wird das Netsh.exe-Tool:

```console
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user
```

Dieser Befehl fügt eine URL-Reservierung für den angegebenen URL-Namespace für das Konto "Domäne\Benutzer". Geben Sie weitere Informationen zur Verwendung von Befehl "Netsh" `netsh http add urlacl /?` in eine Eingabeaufforderung, und drücken Sie die EINGABETASTE.

## <a name="configuring-a-firewall-exception"></a>Konfigurieren einer Firewallausnahme

Beim Selbsthosting eines WCF-Diensts, der über HTTP kommuniziert, muss der Firewallkonfiguration eine Ausnahme hinzugefügt werden, die eingehende Verbindungen über eine bestimmte URL zulässt.

## <a name="configuring-ssl-certificates"></a>Konfigurieren von SSL-Zertifikaten

Das Secure Sockets Layer (SSL)-Protokoll verwendet Zertifikate auf Client und Server, um Verschlüsselungsschlüssel zu speichern. Der Server muss ein SSL-Zertifikat bereitstellen, wenn eine Verbindung hergestellt wird, damit der Client die Identität des Servers überprüfen kann. Der Server kann ebenfalls ein Zertifikat vom Client anfordern, so dass eine wechselseitige Authentifizierung auf beiden Seiten der Verbindung möglich wird.

Zertifikate sind in einem zentralen Speicher entsprechend der IP-Adresse und der Anschlussnummer der Verbindung gespeichert. Die spezielle IP-Adresse 0.0.0.0 stimmt mit jeder IP-Adresse für den lokalen Computer überein. Beachten Sie, dass der Zertifikatspeicher URLs basierend auf dem Pfad unterscheiden nicht. Dienste mit der gleichen Kombination von IP-Adresse und Anschlussnummer müssen die gleichen Zertifikate verwenden, auch wenn sich der Pfad in der URL dieser Dienste unterscheidet.

Schrittweise Anweisungen finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).

## <a name="configuring-the-ip-listen-list"></a>Konfigurieren der IP-Lauschliste

Die HTTP-Server-API stellt erst dann eine Bindung mit einer IP-Adresse und einem Port her, wenn ein Benutzer eine URL registriert. Standardmäßig verbindet die HTTP-Server-API mit dem Anschluss in der URL für alle IP-Adressen des Computers. Ein Konflikt tritt auf, wenn eine Anwendung, die HTTP-Server-API verwenden, nicht, mit dieser Kombination von IP-Adresse und Port bereits gebunden hat. Die IP-Lauschliste ermöglicht WCF-Dienste mit Anwendungen zu koexistieren, die einen Port für einige der IP-Adressen des Computers zu verwenden. Enthält die IP-Lauschliste irgendwelche Einträge, verbindet die HTTP-Server-API nur mit den IP-Adressen, die in der Liste angegeben sind. Die Änderung der IP-Lauschliste erfordert Administratorrechte.

Verwenden Sie das Netsh-Tool die IP-Lauschliste zu ändern, wie im folgenden Beispiel gezeigt:

```console
netsh http add iplisten ipaddress=0.0.0.0:8000
```

## <a name="other-configuration-settings"></a>Andere Konfigurationseinstellungen

Bei Verwendung der <xref:System.ServiceModel.WSDualHttpBinding> verwendet die Clientverbindung Standardwerte, die mit Namespacereservierungen und der Windows-Firewall kompatibel sind. Wenn Sie sich dafür entscheiden, die Clientbasisadresse einer dualen Verbindung anzupassen, müssen Sie diese HTTP-Einstellungen auch auf dem Client mit der neuen Adresse konfigurieren.

Die HTTP-Server-API verfügt über einige erweiterte Konfigurationseinstellungen, die über HttpCfg verfügbar sind. Diese Einstellungen sind in der Registrierung gespeichert und gelten für alle Anwendungen, die auf Systemen laufen, die HTTP-Server-APIs verwenden. Weitere Informationen zu diesen Einstellungen finden Sie unter [Http.sys-registrierungseinstellungen für IIS](https://support.microsoft.com/en-us/help/820129/http-sys-registry-settings-for-windows). Die meisten Benutzer müssen diese Einstellungen zu ändern.

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.WSDualHttpBinding>
- [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md)
