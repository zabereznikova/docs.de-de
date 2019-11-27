---
title: Konformität mit der Konformität von .net Core
description: Erläutert die Konformität von .net Core Federal Information Processing Standard (fps).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205077"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>Konformität von .net Core-Federal Information Processing Standard (fps)

Die Federal Information Processing Standard ()-Veröffentlichung 140-2 ist ein US-Regierungs Standard, der die minimalen Sicherheitsanforderungen für kryptografische Module in Informationstechnologie Produkten definiert, wie in Abschnitt 5131 der Informationen definiert. Technology Management-Reform Act von 1996.

.NET Core:

* Übergibt kryptografische primitive Aufrufe an die Standardmodule, die das zugrunde liegende Betriebssystem bereitstellt.
* Erzwingt **nicht** die Verwendung von per PPS genehmigten Algorithmen oder Schlüsselgrößen in .net Core-apps.

Der Systemadministrator ist für die Konfiguration der Konformität mit der Konformität für ein Betriebssystem verantwortlich.

Wenn Code für eine mit PPS kompatible Umgebung geschrieben wird, ist der Entwickler dafür verantwortlich, sicherzustellen, dass nicht kompatible, nicht kompatible Filter verwendet werden.

Weitere Informationen zur Kompatibilität von Standards finden Sie in den folgenden Artikeln:

* [Windows fi-Konformität](/windows/security/threat-protection/fips-140-validation)
* [Konfigurieren von Windows für die Konformität mit dem PPS](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [10,2. Federal Information Processing Standard (fps)](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
