---
title: BinaryFormatter-Sicherheitsleitfaden
description: In diesem Artikel werden die Sicherheitsrisiken beschrieben, die der Typ BinaryFormatter mit sich bringt. Darüber hinaus werden verschiedene Serialisierungsmodule empfohlen, die verwendet werden können.
ms.date: 07/11/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: f6a54b34bbf1e19212fe37aadb448a1722fe9ff0
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444749"
---
# <a name="binaryformatter-security-guide"></a>BinaryFormatter-Sicherheitsleitfaden

Dieser Artikel bezieht sich auf die folgenden .NET-Implementierungen:

* .NET Framework (alle Versionen)
* .NET Core 2.1–3.1
* .NET 5.0 und höher

## <a name="background"></a>Hintergrund

> [!WARNING]
> Der Typ <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> ist gefährlich und wird für die Datenverarbeitung ***nicht*** empfohlen. Anwendungen sollten so bald wie möglich aufhören, `BinaryFormatter` zu verwenden, auch wenn Sie der Auffassung sind, dass die verarbeiteten Daten vertrauenswürdig sind. `BinaryFormatter` ist unsicher und kann nicht sicher gemacht werden.

Dieser Artikel bezieht sich auch auf die folgenden Typen:

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Web.UI.ObjectStateFormatter>

Sicherheitsrisiken im Zusammenhang mit der Deserialisierung sind eine Bedrohungskategorie, bei der Anforderungsnutzlasten unsicher verarbeitet werden. Ein Angreifer, der diese Sicherheitsrisiken bei einer App erfolgreich nutzt, kann einen Denial of Service (DoS), eine Veröffentlichung von Informationen oder eine Remoteausführung von Code in der Ziel-App bewirken. Diese Risikokategorie ist stets Teil der [OWASP Top 10](https://owasp.org/www-project-top-ten/). Ziele sind Apps in [vielen verschiedenen Sprachen](https://owasp.org/www-community/vulnerabilities/Deserialization_of_untrusted_data), z. B C/C++, Java und C#.

In .NET sind die Ziele mit dem höchsten Risiko Anwendungen, die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> zum Deserialisieren von Daten verwenden. Aufgrund seiner Leistungsfähigkeit und Benutzerfreundlichkeit wird der Typ `BinaryFormatter` im gesamten .NET-Ökosystem häufig verwendet. Genau diese Leistungsfähigkeit ermöglicht es Angreifern jedoch, die Ablaufsteuerung in der Ziel-App zu beeinflussen. Erfolgreiche Angriffe können dazu führen, dass der Angreifer Code im Kontext des Zielprozesses ausführen kann.

Stellen Sie sich als eine einfachere Analogie vor, dass das Aufrufen von `BinaryFormatter.Deserialize` für eine Nutzlast der Interpretation dieser Nutzlast als eigenständige ausführbare Datei und deren Starten entspricht.

## <a name="binaryformatter-security-vulnerabilities"></a>Sicherheitsrisiken bei der Verwendung von BinaryFormatter

> [!WARNING]
> Die Methode `BinaryFormatter.Deserialize` ist __nie__ sicher, wenn sie mit nicht vertrauenswürdigen Eingaben verwendet wird. Es wird dringend empfohlen, dass Benutzer stattdessen die Verwendung einer der weiter unten in diesem Artikel beschriebenen Alternativen in Betracht ziehen.

`BinaryFormatter` wurde implementiert, als Sicherheitsrisiken im Zusammenhang mit der Deserialisierung noch keine so gut erforschte Bedrohungskategorie waren wie heutzutage. Folglich entspricht der Code nicht modernen Best Practices. Die Methode `Deserialize` kann von Angreifern für DoS-Angriffe auf Apps, die diese Methode nutzen, als Vektor verwendet werden. Diese Angriffe können dafür sorgen, dass die App nicht mehr reagiert, oder zu einer unerwarteten Prozessbeendigung führen. Bei dieser Art von Angriff kann das Risiko nicht über `SerializationBinder` oder einen anderen `BinaryFormatter`-Konfigurationsparameter gemindert werden. Dieses Verhalten wird von .NET als ***strukturbedingt*** angesehen, und es wird keine Aktualisierung für den Code zur Änderung dieses Verhaltens veröffentlicht.

`BinaryFormatter.Deserialize` ist möglicherweise auch für andere Arten von Angriffen anfällig, z. B. die Veröffentlichung von Informationen oder die Remoteausführung von Code. Die Verwendung von Features wie einer benutzerdefinierten <xref:System.Runtime.Serialization.SerializationBinder>-Klasse ist möglicherweise unzureichend, um diese Risiken ordnungsgemäß zu mindern. Es besteht die Möglichkeit, dass ein neues Sicherheitsrisiko entdeckt wird, für das .NET praktisch kein Sicherheitsupdate veröffentlichen kann. Benutzer sollten ihre individuellen Szenarios bewerten und die potenzielle Gefahr berücksichtigen, die für sie von diesen Risiken ausgeht.

Es wird empfohlen, dass Benutzer von `BinaryFormatter` individuelle Risikobewertungen für ihre Apps vornehmen. Es liegt in der alleinigen Verantwortung des Benutzers, zu entscheiden, ob er `BinaryFormatter`verwendet. Benutzer sollten Risiken hinsichtlich der Sicherheitsanforderungen sowie technischen, reputationsbezogenen, rechtlichen und aufsichtsrechtlichen Anforderungen für die Verwendung von `BinaryFormatter` bewerten.

## <a name="preferred-alternatives"></a>Bevorzugte Alternativen

.NET bietet mehrere integrierte Serialisierungsmodule, die nicht vertrauenswürdige Daten sicher verarbeiten können:

* Mit <xref:System.Xml.Serialization.XmlSerializer> und <xref:System.Runtime.Serialization.DataContractSerializer> können Objektgraphen in und aus XML serialisiert werden. Verwechseln Sie `DataContractSerializer` allerdings nicht mit <xref:System.Runtime.Serialization.NetDataContractSerializer>.
* <xref:System.IO.BinaryReader> und <xref:System.IO.BinaryWriter> für XML und JSON
* Die <xref:System.Text.Json>-APIs zum Serialisieren von Objektgraphen in JSON

## <a name="dangerous-alternatives"></a>Gefährliche Alternativen

Verwenden Sie nicht die folgenden Serialisierungsmodule:

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.ObjectStateFormatter>

Die obigen Serialisierungsmodule führen alle eine uneingeschränkte polymorphe Deserialisierung durch und sind gefährlich, genau wie `BinaryFormatter`.

## <a name="the-risks-of-assuming-data-to-be-trustworthy"></a>Risiken aufgrund der Annahme der Vertrauenswürdigkeit von Daten

Häufig sind App-Entwickler möglicherweise der Meinung, dass sie nur vertrauenswürdige Eingaben verarbeiten. Eine sichere Eingabe ist nur in ein paar wenigen Fällen gegeben. Viel häufiger ist es so, dass eine Nutzlast die Vertrauenswürdigkeitsgrenze überschreitet, ohne dass dies dem Entwickler bewusst ist.

__Stellen Sie sich einen lokalen Server vor__, bei dem Mitarbeiter einen Desktopclient auf ihren Arbeitsstationen verwenden, um mit dem Dienst zu interagieren. Dieses Szenario kann naiv als „sicheres“ Setup angesehen werden, bei dem die Verwendung von `BinaryFormatter` akzeptabel ist. Es stellt jedoch einen Vektor für Schadsoftware dar, die sich Zugriff auf den Computer eines einzelnen Mitarbeiters verschafft, um sich dann im gesamten Unternehmen verteilen zu können. Diese Schadsoftware kann die Tatsache, dass das Unternehmen `BinaryFormatter` verwendet, nutzen, um lateral von der Arbeitsstation des Mitarbeiters zum Back-End-Server zu wechseln. Sie kann vertrauliche Daten des Unternehmens herausschleusen. Diese Daten könnten Geschäftsgeheimnisse oder Kundendaten enthalten.

__Stellen Sie sich außerdem eine App vor, die `BinaryFormatter` zum Beibehalten des Speicherstatus verwendet.__ Auf den ersten Blick wirkt dies möglicherweise wie ein sicheres Szenario, da das Lesen und Schreiben von Daten auf Ihrer eigenen Festplatte eine nur geringfügige Bedrohung darstellt. Das Teilen von Dokumenten per E-Mail oder über das Internet ist jedoch üblich, und die meisten Endbenutzer würden das Öffnen dieser heruntergeladenen Dateien nicht als riskantes Verhalten ansehen.

Dieses Szenario kann für bösartige Zwecke genutzt werden. Wenn es sich bei der App um ein Spiel handelt, gefährden sich Benutzer, die sichere Dateien teilen, unwissentlich selbst. Die Entwickler selbst können ebenfalls Ziel eines Angriffs werden. Der Angreifer könnte eine E-Mail an den technischen Support des Entwicklers senden, eine schädliche Datendatei anfügen und das Supportpersonal bitten, diese zu öffnen. Diese Art von Angriff könnte dem Angreifer Zugriff auf Unternehmensressourcen verschaffen.

In einem anderen Szenario wird die Datendatei im Cloudspeicher gespeichert und automatisch zwischen den Computern des Benutzers synchronisiert. Ein Angreifer, der Zugriff auf das Cloudspeicherkonto erlangen kann, kann aus der Datendatei eine schädliche Datei machen. Diese Datendatei wird dann automatisch mit den Computern des Benutzers synchronisiert. Wenn der Benutzer die Datendatei das nächste Mal öffnet, wird die Nutzlast des Angreifers ausgeführt. Daher kann der Angreifer eine Kompromittierung des Cloudspeicherkontos nutzen, um vollständige Codeausführungsberechtigungen zu erhalten.

__Stellen Sie sich eine App vor, die von einem Desktopinstallationsmodell zu einem Cloud-First-Modell wechselt.__ Dieses Szenario umfasst Apps, die von einer Desktop-App oder einem Rich-Client-Modell zu einem webbasierten Modell wechseln. Bedrohungsmodelle für die Desktop-App sind nicht notwendigerweise auf den cloudbasierten Dienst anwendbar. Möglicherweise stuft das Bedrohungsmodell für die Desktop-App eine bestimmte Bedrohung als „für den Client, der angegriffen werden soll, nicht relevant“ ein. Dieselbe Bedrohung kann jedoch sehr wohl relevant werden, wenn angenommen wird, dass ein Remotebenutzer (der Client) den Clouddienst selbst angreift.

> [!NOTE]
> Allgemein ist der Zweck der Serialisierung das Übertragen eines Objekts in eine oder aus einer App. Bei Übungen zur Bedrohungsmodellierung wird diese Art von Datenübertragung fast immer als Überschreiten der Vertrauenswürdigkeitsgrenze eingestuft.

## <a name="further-resources"></a>Weitere Ressourcen

* [YSoSerial.Net:](https://github.com/pwntester/ysoserial.net) Erfahren Sie mehr darüber, wie Angreifer Apps angreifen, die `BinaryFormatter` verwenden.
* [Bedrohungsmodellierung:](/securityengineering/sdl/threatmodeling) Informationen zu Apps und Diensten für die Bedrohungsmodellierung
* Allgemeine Hintergrundinformationen zu Sicherheitsrisiken im Zusammenhang mit der Deserialisierung:
  * [OWASP Top 10: A8:2017 – Unsichere Deserialisierung](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A8-Insecure_Deserialization)
  * [CWE-502: Deserialisierung von nicht vertrauenswürdigen Daten](https://cwe.mitre.org/data/definitions/502.html)
