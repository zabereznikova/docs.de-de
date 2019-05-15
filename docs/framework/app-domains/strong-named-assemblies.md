---
title: Assemblys mit starkem Namen
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f87fb330fbea1344cc8532519d358fe8580a9fd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592702"
---
# <a name="strong-named-assemblies"></a>Assemblys mit starkem Namen
Durch die Vergabe eines starken Namens erhalten Assemblys eine eindeutige Identität. Außerdem werden Assemblykonflikte verhindert.  
  
## <a name="what-makes-a-strong-named-assembly"></a>Wodurch zeichnet sich eine Assembly mit starkem Namen aus?  
 Eine Assembly mit starkem Namen wird mithilfe des privaten Schlüssels generiert, der zu dem mit der Assembly verteilten öffentlichen Schlüssel gehört, sowie der Assembly selbst. Die Assembly enthält das Assemblymanifest, das seinerseits die Namen und Hashs aller Dateien enthält, aus denen die Assembly besteht. Assemblys mit demselben starken Namen sollten identisch sein.  
  
 Sie können Assemblys mit starkem Namen mithilfe von Visual Studio oder einem Befehlszeilentool erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) oder [Sn.exe (Strong Name-Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).  
  
 Assemblys mit starkem Namen enthalten den einfachen Textnamen der Assembly, die Versionsnummer, optionale Kulturinformationen, eine digitale Signatur und den öffentlichen Schlüssel, der zu dem für die Signierung verwendeten privaten Schlüssel gehört.  
  
> [!WARNING]
>  Verlassen Sie sich für die Sicherheit nicht auf starke Namen. Diese Namen bieten lediglich eine eindeutige Identität.  
  
## <a name="why-strong-name-your-assemblies"></a>Warum sollten Sie starke Namen für Ihre Assemblys vergeben?  
 Wenn Sie auf eine Assembly mit einem starken Namen verweisen, erhalten Sie dadurch bestimmte Vorteile, z. B. Versions- und Namensschutz. Assemblys mit starkem Namen können im globalen Assemblycache installiert werden, der erforderlich ist, um einige Szenarios zu ermöglichen.  
  
 Assemblys mit starkem Namen sind in den folgenden Szenarien nützlich:  
  
- Auf Ihre Assemblys kann durch Assemblys mit starkem Namen verwiesen werden. Alternativ können Sie den `friend`-Zugriff auf Ihre Assemblys von anderen Assemblys mit starkem Namen ermöglichen.  
  
- Für eine App ist der Zugriff auf verschiedene Versionen derselben Assembly erforderlich. Das bedeutet, dass Sie verschiedene Versionen einer Assembly in derselben App-Domäne nebeneinander ohne Konflikte laden müssen. Wenn z. B. verschiedene Erweiterungen einer API in Assemblys mit demselben einfachen Namen existieren, können Sie durch die Vergabe von starken Namen eine eindeutige Identität für die einzelnen Versionen der Assembly vergeben.  
  
- Die Assembly sollte domänenneutral sein, um eine Beeinträchtigung der Leistung der Apps zu vermeiden, die auf Ihre Assembly zugreifen. Dies erfordert starke Namen, da eine domänenneutrale Assembly im globalen Assemblycache installiert werden muss.  
  
- Wenn Sie den Service für Ihre App durch Anwendung einer Herausgeberrichtlinie zentralisieren möchten (d.h. wenn die Assembly im globalen Assemblycache installiert ist).  
  
 Wenn Sie Open Source-Entwickler sind und die Vorzüge von Assemblys mit starkem Namen kennen lernen möchten, können Sie unter Umständen den privaten Schlüssel einer Assembly zusammen in Ihr Quellcodeverwaltungssystem einchecken.  
  
## <a name="see-also"></a>Siehe auch

- [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)
- [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [Sn.exe (Strong Name-Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)
- [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
