---
title: .NET Core-Versionsverlauf
description: Sehen Sie sich den zeitlichen Verlauf der Versionen der .NET Core-Runtime, des .NET Core SDK, des C#-Compilers und des VB.NET-Compilers an.
ms.date: 07/26/2018
ms.openlocfilehash: 90fd4ba57620a3a005f2148c0335a76a6fa54a30
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936632"
---
# <a name="net-core-version-history"></a>.NET Core-Versionsverlauf

Versionsnummern für .NET Core stellen eine Herausforderung dar, weil das .NET Core SDK und die .NET Core-Runtime in einem unterschiedlichen Rhythmus veröffentlicht werden. Durch die unterschiedlichen Rhythmen muss das Team nur zwei der folgenden drei Faktoren beachten:

1. Unabhängige Veröffentlichung, sodass sich Tools, C# und VB schneller als die .NET Core-Runtime entwickeln können.
2. Aufrechterhalten von übereinstimmenden Versionsnummern zwischen dem .NET Core SDK und der .NET Core-Runtime.
3. Semantische Versionierung für das .NET Core SDK und die .NET Core-Runtime.

Mit 2.0.0 mussten die Versionen übereinstimmen und waren für ein Release fortlaufend. Im Dezember 2017 wurde ein Featurerelease für das .NET Core SDK ohne entsprechendes Release für die .NET Core-Runtime veröffentlicht. Das Team hält sich nur noch an das erste und das dritte Ziel und konzentriert sich nicht mehr auf übereinstimmende Versionen für die .NET Core-Runtime und das .NET Core SDK. Es wurden mehrere .NET Core SDK 2.1.x-Versionen veröffentlicht, bevor die .NET Core-Runtime 2.1 veröffentlicht wurde. Da das SDK nicht aufwärtskompatibel ist, können diese 2.1.x-SDK-Versionen nicht für die .NET Core-Runtime 2.1 verwendet werden. Das Team hat auf die Verwirrung bezüglich der Versionen reagiert und ist dazu übergegangen, das erste und zweite Ziel zu berücksichtigen. Somit wurde die semantische Versionierung wie unter [.NET Core-Versionskontrolle](index.md#versioning-details) beschrieben aufgegeben.

Nach der Aufgabe der semantischen Versionierung wurden Übergangsreleases im Versionsnummerbereich zwischen 2.1.10x und 2.1.20x veröffentlicht, die auch nicht für die .NET Core-Runtime 2.1 verwendet werden können.

Die ersten beiden Ziffern der Versionsnummer entsprechen wieder der Version 2.1.0 der .NET Core-Runtime und der Version 2.1.300 des .NET Core SDK.

Ausführliche Informationen zu den Versionen einzelner Komponenten, u.a. Framework- und Sprachcompilerversionen, finden Sie auf der [Downloadseite von .NET Core](https://www.microsoft.com/net/download/dotnet-core/current). Ausführliche Informationen zu vorherigen Versionen erhalten Sie, wenn Sie auf die jeweilige Version auf der [Archivseite der Downloads von .NET Core](https://www.microsoft.com/net/download/archives) klicken. Ausführliche Informationen zu Support finden Sie im Artikel zur offiziellen [.NET-Supportrichtlinie](https://www.microsoft.com/net/Support/Policy).