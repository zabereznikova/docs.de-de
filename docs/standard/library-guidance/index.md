---
title: Leitfaden für die Open Source-Bibliothek
description: Empfehlungen für bewährte Methoden für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 10/17/2018
ms.openlocfilehash: ca95cb5ba1ebf27464397b7850ac02aabded1a5b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188624"
---
# <a name="open-source-library-guidance"></a>Leitfaden für die Open Source-Bibliothek

Dieser Leitfaden bietet Empfehlungen für Entwickler zum Erstellen von qualitativ hochwertigen .NET-Bibliotheken. In dieser Dokumentation liegt der Fokus auf dem *Was* und *Warum* beim Erstellen einer .NET-Bibliothek und nicht auf dem *Wie*.

Aspekte hochqualitativer Open Source-Bibliotheken für .NET:

> [!div class="checklist"]
> * **Inklusiv:** Gute .NET-Bibliotheken sind dafür ausgelegt, viele Plattformen, Programmiersprachen und Anwendungen zu unterstützen.
> * **Stabil:** Gute .NET-Bibliotheken existieren im .NET-Ökosystem nebeneinander und werden in Anwendungen ausgeführt, die mit vielen Bibliotheken erstellt wurden.
> * **Für die Weiterentwickelung entworfen:** .NET-Bibliotheken sollten sich im Laufe der Zeit verbessern und weiterentwickeln, während Sie vorhandene Benutzer unterstützen.
> * **Debugfähig:** .NET-Bibliotheken sollten die neuesten Tools verwenden, um für Benutzer eine gute Debugleistung bereitzustellen.
> * **Vertrauenswürdig:** Entwickler haben Vertrauen zu .NET-Bibliotheken, da diese mithilfe bewährter Sicherheitsmethoden Inhalte auf NuGet veröffentlichen.

> [!div class="nextstepaction"]
> [Erste Schritte](./get-started.md)

## <a name="types-of-recommendations"></a>Empfehlungstypen

Jeder Artikel enthält vier Empfehlungstypen: **Do**, **Erwägen**, **Vermeiden** und **Do not**. Der Empfehlungstyp kennzeichnet, wie streng die Empfehlung befolgt werden sollte.

Eine **Do**-Empfehlung sollten Sie fast immer befolgen. Zum Beispiel:

**✔️ DO** Verteilen Sie Ihre Bibliothek mithilfe eines NuGet-Pakets.

Andererseits gibt es Empfehlungen, die Sie **erwägen** sollten. Berechtigte Ausnahmen bestätigen jedoch die Regel, und es ist auch nicht weiter schlimm, wenn Sie die folgende Anweisung nicht befolgen:

**✔️ ERWÄGEN** Sie, [SemVer 2.0.0](https://semver.org/) für die Versionskontrolle Ihres NuGet-Pakets zu verwenden.

Empfehlungen hinsichtlich **Vermeiden** geben Dinge an, die allgemein als keine gute Idee angesehen werden, jedoch kann das Brechen dieser Regel manchmal auch sinnvoll sein:

**❌ VERMEIDEN** Sie NuGet-Paketverweise, die eine exakte Version erfordern.

Schließlich kennzeichnen **Do not**-Empfehlungen Vorgänge, die Sie niemals ausführen sollten:

**❌ DON‘T** Veröffentlichen Sie keine Versionen mit starkem Namen oder nicht starkem Namen Ihrer Bibliothek. Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.

>[!div class="step-by-step"]
[Nächste](./get-started.md)
