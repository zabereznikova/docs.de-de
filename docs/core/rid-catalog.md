---
title: .NET Core Runtime-ID-Katalog (RID) | Microsoft-Dokumentation
description: .NET Core Runtime-ID-Katalog (RID)
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 904b9be05cd2e5337272ce7ddce15b1075fbefeb
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---

<a id="net-core-runtime-identifier-rid-catalog" class="xliff"></a>

# .NET Core Runtime-ID-Katalog (RID)

<a id="what-are-rids" class="xliff"></a>

## Was sind RIDs?
RID ist die Kurzform für *Runtime-ID* (Laufzeitbezeichner). RIDs dienen zur Identifizierung von Zielbetriebssystemen, in denen eine Anwendung oder ein Objekt (d.h. eine Assembly) ausgeführt wird. Sie sehen folgendermaßen aus: „ubuntu.14.04 x64“, „win7-x64“, „osx.10.11-x64“. Für die Pakete mit nativen Abhängigkeiten legt er fest, auf welchen Plattformen das Paket wiederhergestellt werden kann. 

Es ist wichtig zu beachten, dass die RIDs tatsächlich opake Zeichenfolgen sind. Dies bedeutet, dass sie für Vorgänge, die mit ihnen arbeiten, genau übereinstimmen müssen. Als Beispiel betrachten wir [Elementary OS](https://elementary.io/), welches ein einfacher Klon von Ubuntu 14.04 ist. Obwohl .NET Core und CLI zusätzlich zu dieser Version von Ubuntu funktionieren, schlägt der Wiederherstellungsvorgang für jedes Paket fehl, wenn Sie versuchen, Elementary OS ohne Änderungen zu verwenden. Dies liegt daran, dass wir momentan keine RID haben, die Elementary OS als Plattform festlegt. 

RIDs, die konkrete Betriebssysteme darstellen, weisen in der Regel folgendes Muster auf: `[os].[version]-[arch]`, wobei:
- `[os]` ist der Moniker des Betriebssystems, z.B. `ubuntu`.
- `[version]` die Version des Betriebssystems in Form einer mit Punkt (`.`) getrennten Versionsnummer ist, z.B. `15.10`, die genau genug ist, um Ressourcen den Zugriff auf Betriebssystems- APIs, die diese Versionskennung verwenden, zu ermöglichen.
  - Dies sollten **keine** Marketingversionen sein, da diese häufig mehrere separate Versionen des Betriebssystems mit unterschiedlichen Plattform-API-Oberflächen darstellen.
- `[arch]` ist die Prozessorarchitektur, z.B. `x86`, `x64`, `arm`, `arm64` usw.

Das RID-Diagramm wird in einem Paket namens `Microsoft.NETCore.Platforms` in einer Datei namens `runtime.json` definiert, die Sie dem [CoreFX-Repository](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) entnehmen können. Wenn Sie diese Datei verwenden, werden Sie feststellen, dass einige der RIDs eine `"#import"`-Anweisung beinhalten. Diese Anweisungen sind Kompatibilitätsanweisungen. Das bedeutet, dass eine RID, die eine importierte RID enthält, als Ziel für das Wiederherstellen von Paketen für diese RID verwendet werden kann. Das erscheint etwas verwirrend, aber sehen wir uns ein Beispiel an. Betrachten wir macOS:

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
Die oben genannte RID gibt an, dass `osx.10.11-x64` `osx.10.10-x64` importiert. Dies bedeutet, dass NuGet beim Wiederherstellen von Paketen in der Lage ist, Pakete wiederherzustellen, die angeben, dass sie `osx.10.11-x64` unter `osx.10.10-x64` benötigen.

Ein etwas größeres Beispiel-RID-Diagramm:  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

Alle RIDs bilden schließlich wieder den Stamm `any`-RID ab.

Obwohl ihre Anwendung einfach scheint, gibt es bei RIDs einige Besonderheiten, die Sie bedenken sollten, wenn Sie mit ihnen arbeiten:

* Sie sind **opake Zeichenfolgen** und sollten als Blackbox behandelt werden
    * Sie sollten keine RIDs programmgesteuert erstellen
* Sie müssen die RIDs verwenden, die bereits für die Plattform definiert sind, was diesem Dokument zu entnehmen ist
* Die RIDs müssen nicht spezifisch sein, gehen Sie daher nicht von dem tatsächlichen RID-Wert aus. Anhand der Informationen in diesem Dokument können Sie bestimmen, welche RID(s) Sie für eine bestimmte Plattform benötigen

<a id="using-rids" class="xliff"></a>

## Die Verwendung von RIDs
Um RIDs zu verwenden, müssen Sie wissen, welche RIDs es gibt. Zur Plattform werden regelmäßig neue RIDs hinzugefügt. Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) im CoreFX-Repository auf die neueste Version.

> [!NOTE]
> Wir arbeiten daran, diese Informationen in eine interaktivere Form zu bringen. Sobald dies der Fall ist, wird diese Seite aktualisiert werden und Sie auf dieses Tool bzw. die Dokumentation zur Verwendung hinweisen. 

<a id="windows-rids" class="xliff"></a>

## RIDs für Windows

* Windows 7 / Windows Server 2008 R2
    * `win7-x64`
    * `win7-x86`
* Windows 8 / Windows Server 2012
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* Windows 8.1 / Windows Server 2012 R2
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* Windows 10 / Windows Server 2016
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

<a id="linux-rids" class="xliff"></a>

## RIDs für Linux

* Red Hat Enterprise Linux
    * `rhel.7-x64`
* Ubuntu
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* CentOS
    * `centos.7-x64`
* Debian
    * `debian.8-x64`
* Fedora
    * `fedora.23-x64`
    * `fedora.24-x64`
* OpenSUSE
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* Oracle Linux
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* Derzeit unterstützte Derivate von Ubuntu 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

<a id="os-x-rids" class="xliff"></a>

## RIDs für OS X

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`

