---
title: Leitfaden für die Open Source-Bibliothek
description: Empfehlungen für bewährte Methoden für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 50fb745f7eb65abcaca76cebaf9991c48f559e59
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374900"
---
# <a name="open-source-library-guidance"></a>Leitfaden für die Open Source-Bibliothek

Dieser Leitfaden bietet Empfehlungen für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken. In dieser Dokumentation liegt der Fokus auf dem *Was* und *Warum* beim Erstellen einer .NET-Bibliothek und nicht auf dem *Wie*.

Aspekte hochqualitativer Open Source-Bibliotheken für .NET:

> [!div class="checklist"]
> * **Inklusiv:** Gute .NET-Bibliotheken sind dafür ausgelegt, viele Plattformen und Anwendungen zu unterstützen.
> * **Stabil:** Gute .NET-Bibliotheken existieren im .NET-Ökosystem nebeneinander und werden in Anwendungen ausgeführt, die mit vielen Bibliotheken erstellt wurden.
> * **Für die Weiterentwickelung entworfen:** .NET-Bibliotheken sollten sich im Laufe der Zeit verbessern und weiterentwickeln, während Sie vorhandene Benutzer unterstützen.
> * **Debugfähig:** .NET-Bibliotheken sollten die neuesten Tools verwenden, um für Benutzer eine gute Debugleistung bereitzustellen.
> * **Vertrauenswürdig:** Entwickler haben Vertrauen zu .NET-Bibliotheken, da diese mithilfe bewährter Sicherheitsmethoden Inhalte auf NuGet veröffentlichen.

> [!div class="nextstepaction"]
> [Erste Schritte](./get-started.md)

## <a name="recommendations"></a>Empfehlungen

Mit jedem Artikel wird eine Liste der Empfehlungen für Ihre .NET-Bibliothek mit Aktionen veröffentlicht, die Sie **tun**, **erwägen**, **vermeiden** und **keinesfalls tun** sollten. Der Wortlaut jeder Empfehlung lässt darauf schließen, wie streng diese befolgt werden sollte.

Eine **DO**-Empfehlung sollten Sie so gut wie immer befolgen:

**✔️ DO** Verteilen Sie Ihre Bibliothek mithilfe eines NuGet-Pakets.

Andererseits gibt es Empfehlungen, die Sie **erwägen** sollten. Berechtigte Ausnahmen bestätigen jedoch die Regel, und es ist auch nicht weiter schlimm, wenn Sie die folgende Anweisung nicht befolgen:

**✔️ ERWÄGEN** Sie, [SemVer 2.0.0](https://semver.org/) für die Versionskontrolle Ihres NuGet-Pakets zu verwenden.

Empfehlungen zur **Vermeidung** stehen für Dinge, die allgemein als keine gute Idee angesehen werden, jedoch kann das Brechen dieser Regel manchmal auch sinnvoll sein:

**❌ VERMEIDEN** Sie NuGet-Paketverweise, die eine exakte Version erfordern.

Schließlich gibt es noch Dinge, die Sie **keinesfalls tun sollten**:

**❌ DON‘T** Veröffentlichen Sie keine Versionen mit starkem Namen oder nicht starkem Namen Ihrer Bibliothek. Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.

>[!div class="step-by-step"]
[Nächste](./get-started.md)
