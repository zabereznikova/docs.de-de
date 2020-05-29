---
title: Assemblys mit starkem Namen
description: Erfahren Sie mehr über starke Namen für .NET-Assemblys, die eine eindeutige Identität des Assemblys schaffen und Assemblykonflikte verhindern können.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
ms.openlocfilehash: a2db0efcb57226a757796c311309ce8f749a398b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378601"
---
# <a name="strong-named-assemblies"></a>Assemblys mit starkem Namen

Durch die Vergabe eines starken Namens erhalten Assemblys eine eindeutige Identität. Außerdem werden Assemblykonflikte verhindert.

## <a name="what-makes-a-strong-named-assembly"></a>Wodurch zeichnet sich eine Assembly mit starkem Namen aus?

Eine Assembly mit starkem Namen wird mithilfe des privaten Schlüssels generiert, der zu dem mit der Assembly verteilten öffentlichen Schlüssel gehört, sowie der Assembly selbst. Die Assembly enthält das Assemblymanifest, das seinerseits die Namen und Hashs aller Dateien enthält, aus denen die Assembly besteht. Assemblys mit demselben starken Namen sollten identisch sein.

Sie können Assemblys mit starkem Namen mithilfe von Visual Studio oder einem Befehlszeilentool erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit starkem Namen ](sign-strong-name.md) oder [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md).

Assemblys mit starkem Namen enthalten den einfachen Textnamen der Assembly, die Versionsnummer, optionale Kulturinformationen, eine digitale Signatur und den öffentlichen Schlüssel, der zu dem für die Signierung verwendeten privaten Schlüssel gehört.

> [!WARNING]
> Verlassen Sie sich für die Sicherheit nicht auf starke Namen. Diese Namen bieten lediglich eine eindeutige Identität.

## <a name="why-strong-name-your-assemblies"></a>Warum sollten Sie starke Namen für Ihre Assemblys vergeben?

Wenn Sie auf eine Assembly mit einem starken Namen verweisen, erhalten Sie dadurch bestimmte Vorteile, z. B. Versions- und Namensschutz. Assemblys mit starkem Namen können im .NET Framework im globalen Assemblycache installiert werden, was für einige Szenarios erforderlich ist.

Assemblys mit starkem Namen sind in den folgenden Szenarien nützlich:

- Auf Ihre Assemblys kann durch Assemblys mit starkem Namen verwiesen werden. Alternativ können Sie den `friend`-Zugriff auf Ihre Assemblys von anderen Assemblys mit starkem Namen ermöglichen.

- Für eine App ist der Zugriff auf verschiedene Versionen derselben Assembly erforderlich. Das bedeutet, dass Sie verschiedene Versionen einer Assembly in derselben App-Domäne nebeneinander ohne Konflikte laden müssen. Wenn z. B. verschiedene Erweiterungen einer API in Assemblys mit demselben einfachen Namen existieren, können Sie durch die Vergabe von starken Namen eine eindeutige Identität für die einzelnen Versionen der Assembly vergeben.

- Die Assembly sollte domänenneutral sein, um eine Beeinträchtigung der Leistung der Apps zu vermeiden, die auf Ihre Assembly zugreifen. Dies erfordert starke Namen, da eine domänenneutrale Assembly im globalen Assemblycache installiert werden muss.

- Sie möchten die Wartung Ihrer App durch Anwendung einer Verlegerrichtlinie zentralisieren. Die Assembly muss daher im globalen Assemblycache installiert sein.

Wenn Sie Open-Source-Entwickler sind und den Nutzen von Assemblys mit starkem Namen ermitteln möchten, können Sie den privaten Schlüssel zusammen mit der zugehörigen Assembly in Ihr Quellcodeverwaltungssystem einchecken.

## <a name="see-also"></a>Siehe auch

- [Globaler Assemblycache](../../framework/app-domains/gac.md)
- [How to: Signieren einer Assembly mit einem starken Namen](sign-strong-name.md)
- [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
