---
title: Migrieren vorhandener .NET-Apps zu Azure-IaaS mittels Lift & Shift (cloudinfrastrukturfähig)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern.
ms.date: 04/28/2018
ms.openlocfilehash: d610222aa6649c1b28e198c074794dd316f895ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172169"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Migrieren vorhandener .NET-Apps zu Azure-IaaS mittels Lift & Shift (cloudinfrastrukturfähig)

> Vision: Als ersten Schritt, um Ihre lokalen Investitionen und die Gesamtkosten für die Hardware- und Netzwerkwartung zu verringern, hosten Sie einfach Ihre vorhandenen Anwendungen neu in der Cloud.

Bevor wir in die Details gehen, *wie* Sie Ihre vorhandenen Anwendungen zur Azure IaaS-Plattform (Infrastructure-as-a-Service) migrieren, ist es wichtig, die Gründe zu analysieren, *warum* Sie direkt zu IaaS in Azure migrieren möchten. Das Szenario bei diesem Modernisierungsreifegrad liegt im Wesentlichen darin, mit der Verwendung von VMs in der Cloud zu beginnen, anstatt weiterhin Ihre aktuelle lokale Infrastruktur zu verwenden.

Ein weiterer Punkt, der analysiert werden sollte, ist, *warum* Sie zu einer reinen IaaS-Cloud migrieren möchten, anstatt nur komplexere verwaltete Dienste in Azure hinzuzufügen. Bestimmen Sie, für welche Fälle IaaS in erster Linie erforderlich ist.

In Abbildung 2-1 werden cloudinfrastrukturfähige Anwendungen in den Modernisierungsreifegraden positioniert:

![Positionierung von cloudinfrastrukturfähigen Anwendungen](./media/image2-1.png)

**Abbildung 2-1.** Positionierung von cloudinfrastrukturfähigen Anwendungen

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Warum vorhandene .NET-Webanwendungen zu Azure IaaS migrieren?

Der Hauptgrund für die Migration in die Cloud, auch auf einer ersten IaaS-Ebene, besteht darin, Kostensenkungen zu erzielen. Durch die Verwendung von mehr verwalteten Infrastrukturdiensten kann Ihre Organisation Ihre Investitionen in die Hardwarewartung, Server- oder VM-Bereitstellung und Infrastrukturverwaltung senken.

Nachdem Sie die Entscheidung getroffen haben, Ihre Apps in die Cloud zu verlagern, ist der Hauptgrund für die Wahl von IaaS anstelle von komplexeren Optionen wie PaaS einfach der, dass die IaaS-Umgebung vertrauter sein wird. Beim Umzug in eine Umgebung, die Ihrer aktuellen lokalen Umgebung ähnelt, bietet die lokale Umgebung eine flachere Lernkurve, was dies zum schnellsten Weg in die Cloud macht.

Der schnellste Weg in die Cloud bedeutet jedoch nicht, dass Sie den größten Nutzen daraus ziehen, dass Ihre Anwendungen in der Cloud laufen. Jede Organisation profitiert von einer Cloudmigration mit den bereits eingeführten Reifegraden „Cloud-Optimized“ und „Cloud-Native“ am meisten.

Es hat sich auch gezeigt, dass Anwendungen in Zukunft einfacher zu modernisieren und umzubauen sind, wenn sie bereits in der Cloud ausgeführt werden, auch in IaaS. Die Migration von Anwendungsdaten wurde bereits durchgeführt. Außerdem hat Ihre Organisation die für die Arbeit in der Cloud erforderlichen Fähigkeiten bereits erworben und den Wechsel zum Betrieb in einer „Cloudkultur“ vollzogen.

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Wann zu IaaS anstatt zu PaaS migrieren?

In den nächsten Abschnitten werden „Cloud-Optimized“-Anwendungen behandelt, die überwiegend auf PaaS-Plattformen und -Diensten basieren. Diese Apps bieten Ihnen die meisten Vorteile durch die Migration zur Cloud.

Wenn Ihr Ziel einfach darin besteht, bestehende Anwendungen in die Cloud zu verschieben, identifizieren Sie zunächst bestehende Anwendungen, die keine wesentlichen Änderungen erfordern würden, um sie in Azure App Service auszuführen. Diese Apps sollten die ersten Kandidaten für „Cloud-Optimized“ sein.

Migrieren Sie dann die Apps, die nach wie vor nicht in Windows-Container und PaaS verschoben werden können (z. B. App Service oder Orchestratoren wie Azure Kubernetes Service), zu einfachen VMs (IaaS).

Beachten Sie jedoch, dass die korrekte Konfiguration, Sicherung und Wartung von VMs viel mehr Zeit und IT-Kenntnisse erfordert, als die Nutzung von PaaS-Diensten in Azure. Wenn Sie die Nutzung von Azure Virtual Machines in Erwägung ziehen, müssen Sie den fortlaufenden Wartungsaufwand berücksichtigen, der für das Patchen, Aktualisieren oder Verwalten der VM-Umgebung erforderlich ist. Virtuelle Azure-Computer sind IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Verwenden Sie Azure Migrate, um Ihre vorhandenen Anwendungen zu analysieren und zu Azure zu migrieren.

Die Migration zur Cloud muss nicht schwierig sein. Viele Organisationen haben jedoch Probleme beim Einstieg, um einen tiefen Einblick in die Umgebung und die engen Abhängigkeiten zwischen Anwendungen, Workloads und Daten zu erhalten. Ohne diesen Einblick kann es schwierig sein, den weitergehenden Pfad zu planen. Ohne detaillierte Informationen zu den Voraussetzungen für eine erfolgreiche Migration können Sie in Ihrer Organisation nicht die richtigen Unterhaltungen führen. Sie wissen nicht genug über die potenziellen Kostenvorteile, oder ob Workloads einfach nur per Lift & Shift migriert werden können oder eine beträchtliche Neubearbeitung erfordern, um erfolgreich migriert zu werden. Kein Wunder, dass viele Unternehmen zögern.

[Azure Migrate](https://aka.ms/azuremigrate) ist eine neuer Dienst, der Anleitung, Einblicke und Mechanismen bietet, die erforderlich sind, um Sie bei der Migration zu Azure zu unterstützen. Azure Migrate bietet:

- Ermittlung und Bewertung für lokale virtuelle Computer

- Integrierte Abhängigkeitszuordnung für die hoch zuverlässige Ermittlung von Anwendungen mit mehreren Schichten

- Intelligente richtige Größenbestimmung für virtuelle Azure-Computer

- Kompatibilitätsberichte mit Richtlinien zum Beheben potenzieller Probleme

- Integration in Azure Database Management Service für Datenbankermittlung und -migration

Azure Migrate bietet Ihnen die Gewissheit, dass Ihre Workloads mit minimalen Auswirkungen auf das Unternehmen migriert und erwartungsgemäß in Azure ausgeführt werden können. Mit den richtigen Tools und Anleitungen können Sie eine maximale Rendite erzielen und gleichzeitig sicherstellen, dass wichtige Anforderungen an Leistung und Zuverlässigkeit erfüllt werden.

In Abbildung 2-2 wird die integrierte Abhängigkeitszuordnung für alle Server- und Anwendungsverbindungen gezeigt, die von Azure Migrate hergestellt werden.

![Positionierung von cloudinfrastrukturfähigen Anwendungen](./media/image2-2.png)

**Abbildung 2–2.** Positionierung von cloudinfrastrukturfähigen Anwendungen

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Verwenden von Azure Site Recovery, um Ihre vorhandenen VMs zu Azure-VMs zu migrieren

Als Teil von End-to-End-[Azure Migrate](https://aka.ms/azuremigrate) ist [Azure Site Recovery](/azure/site-recovery/site-recovery-overview) ein Tool, mit dem Sie Ihre Web-Apps problemlos zu virtuellen Computern in Azure migrieren können. Sie können Site Recovery verwenden, um lokale VMs und physische Server in Azure zu synchronisieren oder um sie an einen sekundären lokalen Ort zu replizieren. Sie können sogar eine Workload replizieren, die auf einem unterstützten virtuellen Azure-Computer, auf einem lokalen virtuellen *Hyper-V*-Computer, auf einem virtuellen *VMware*-Computer oder auf einem physischen Windows- oder Linux-Server ausgeführt wird. Mit der Replikation in Azure entfallen die Kosten und die Komplexität, die mit der Verwaltung eines sekundären Datencenters verbunden sind.

Site Recovery ist auch speziell auf Hybridumgebungen ausgelegt, die sich teilweise lokal und teilweise in Azure befinden. Site Recovery sorgt für Geschäftskontinuität, indem es Ihre Apps, die auf VMs und lokalen physischen Servern ausgeführt werden, verfügbar hält, wenn ein Standort ausfällt. Es repliziert Workloads, die auf VMs und physischen Servern ausgeführt werden, damit sie an einem sekundären Ort verfügbar bleiben, wenn die Verfügbarkeit des primären Standorts nicht mehr gegeben ist. Workloads werden am primären Standort wiederhergestellt, wenn er wieder betriebsbereit ist.

In Abbildung 2-3 wird die Ausführung mehrerer VM-Migrationen mithilfe von Azure Site Recovery veranschaulicht.

![Positionierung von cloudinfrastrukturfähigen Anwendungen](./media/image2-3.png)

**Abbildung 2-3.** Positionierung von cloudinfrastrukturfähigen Anwendungen

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Azure Migrate-Datenblatt**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure-Migrationscenter**

    <https://azure.microsoft.com/migration/>

- **Durchführen der Migration zu Azure mit Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Azure Site Recovery-Dienstübersicht**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migrieren von VMs in AWS zu virtuellen Azure-Computern**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
