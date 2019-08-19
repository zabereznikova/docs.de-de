---
title: Migrieren und Verschieben vorhandener .net-apps in Azure IaaS (cloudinfrastruktur-bereit)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern.
ms.date: 04/28/2018
ms.openlocfilehash: cda316ad01a58f26661395c804547de04e20d052
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578393"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Migrieren und Verschieben vorhandener .net-apps in Azure IaaS (cloudinfrastruktur-bereit)

> Vision: Als ersten Schritt sollten Sie Ihre vorhandenen Anwendungen einfach in der Cloud neu hosten, um Ihre lokalen Investitionen und die Gesamtkosten für die Hardware-und Netzwerk Wartung zu verringern.

Bevor Sie sich mit der Migration vorhandener Anwendungen zur Azure Infrastructure as a Service (IaaS)-Plattform befassen, *sollten* Sie die Gründe für die direkte Migration zu IaaS in Azure analysieren. Das Szenario auf dieser Modernisierungs Reife liegt im Wesentlichen darin, VMS in der Cloud zu verwenden, anstatt weiterhin Ihre aktuelle lokale Infrastruktur zu verwenden.

Ein weiterer Punkt, der analysiert werden kann, ist der *Grund, warum* Sie zu einer reinen IaaS-Cloud migrieren möchten, anstatt einfach erweiterte verwaltete Dienste in Azure hinzuzufügen. Legen Sie fest, für welche Fälle zuerst IaaS erforderlich sind.

In Abbildung 2-1 werden cloudinfrastrukturfähige Anwendungen in den Modernisierungs Reifegraden positioniert:

![Positionieren von cloudinfrastrukturfähigen Anwendungen](./media/image2-1.png)

> **Abbildung 2-1.** Positionieren von cloudinfrastrukturfähigen Anwendungen

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Gründe für die Migration vorhandener .NET-Webanwendungen zu Azure IaaS

Der Hauptgrund für die Migration in die Cloud, auch auf der ersten IaaS-Ebene, besteht darin, Kostensenkungen zu erzielen. Durch die Verwendung von mehr verwalteten Infrastruktur Diensten kann Ihre Organisation die Investitionen in die Hardware Wartung, die Bereitstellung und Bereitstellung von Server-oder VM-bereit Stellungen und die Infrastruktur Verwaltung senken.

Wenn Sie die Entscheidung getroffen haben, Ihre apps in die Cloud zu verlagern, ist der Hauptgrund, warum Sie IaaS anstelle von erweiterten Optionen wie z.b. "Pas" auswählen können, einfach die IaaS-Umgebung vertraut zu machen. Die Umstellung auf eine Umgebung, die Ihrer aktuellen, lokalen Umgebung ähnelt, bietet eine geringere Lernkurve, die den schnellsten Weg zur Cloud macht.

Der schnellste Weg zur Cloud bedeutet jedoch nicht, dass Sie am meisten davon profitieren, dass Ihre Anwendungen in der Cloud ausgeführt werden. Jede Organisation erhält die wichtigsten Vorteile von einer cloudmigration auf den bereits eingeführten cloudoptimierten und cloudbasierten Reifegraden.

Es ist auch offensichtlich, dass Anwendungen in Zukunft einfacher zu modernisieren und zu entwerfen sind, wenn Sie bereits in der Cloud ausgeführt werden, auch in IaaS. Die Migration von Anwendungsdaten wurde bereits durchgeführt. Außerdem erhält Ihre Organisation Kenntnisse, die für die Arbeit in der Cloud erforderlich sind, und hat den Betrieb in eine "cloudkultur" verlagert.

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Bei der Migration zu IaaS anstelle von zu "Pas"

In den nächsten Abschnitten werden Cloud-optimierte Anwendungen erläutert, die größtenteils auf den Plattformen und Diensten von Pas basieren. Diese Apps bieten Ihnen die meisten Vorteile von der Migration zur Cloud. 

Wenn Sie lediglich vorhandene Anwendungen in die Cloud verschieben möchten, müssen Sie zunächst vorhandene Anwendungen identifizieren, für die keine beträchtlichen Änderungen erforderlich sind, um Sie in Azure App Service auszuführen. Diese apps sollten die ersten Kandidaten für die Cloud-Optimierung sein. 

Migrieren Sie dann für die apps, die nach wie vor nicht in Windows-Container und-Paare (z. b. app Service oder orchestratoren wie Azure Kubernetes Service) verschoben werden können, diese zu einfachen einfachen VMS (IaaS). 

Denken Sie jedoch daran, dass die ordnungsgemäße Konfiguration, Sicherung und Wartung von VMS viel mehr Zeit und IT-Fachkenntnisse im Vergleich zur Verwendung von Azure-Diensten in Azure erfordert. Wenn Sie Azure Virtual Machines in Erwägung ziehen, müssen Sie sicherstellen, dass Sie den fortlaufenden Wartungsaufwand für das Patchen, aktualisieren und Verwalten Ihrer VM-Umgebung berücksichtigen. Azure-Virtual Machines ist IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Verwenden von Azure migrate zum Analysieren und Migrieren vorhandener Anwendungen zu Azure

Die Migration zur Cloud muss nicht schwierig sein. Viele Unternehmen sind jedoch gezwungen, loszulegen, um einen tiefen Einblick in die Umgebung und die engen Abhängigkeiten zwischen Anwendungen, Workloads und Daten zu erhalten. Ohne diese Sichtbarkeit kann es schwierig sein, den Pfad vorwärts zu planen. Ohne detaillierte Informationen zu den Voraussetzungen für eine erfolgreiche Migration können Sie in Ihrer Organisation nicht die richtigen Konversationen durchführen. Sie wissen nicht genug über die potenziellen Kostenvorteile, oder ob Arbeits Auslastungen einfach nur eine Lift-and-Shift-Funktion oder eine beträchtliche Neuverarbeitung erfordern, um erfolgreich migriert zu werden. Kein Wunder, dass viele Unternehmen zögern.

[Azure migrate](https://aka.ms/azuremigrate) ist ein neuer Dienst, der Anleitungen, Einblicke und Mechanismen bietet, die Sie bei der Migration zu Azure unterstützen müssen. Azure migrate bietet Folgendes:

- Ermittlung und Bewertung für lokale virtuelle Computer

- Integrierte Abhängigkeits Zuordnung für die hoch Vertrauensstellung von Anwendungen mit mehreren Ebenen

- Intelligent right Sizing to Azure Virtual Machines

- Kompatibilitäts Berichte mit Richtlinien zum Beheben potenzieller Probleme

- Integration in Azure Database Management Service für die Daten Bank Ermittlung und-Migration

Azure migrate bietet Ihnen die Gewissheit, dass Ihre Workloads mit minimalen Auswirkungen auf das Unternehmen migriert und erwartungsgemäß in Azure ausgeführt werden können. Mit den richtigen Tools und Anleitungen können Sie eine maximale Rendite erzielen und gleichzeitig sicherstellen, dass wichtige Anforderungen an Leistung und Zuverlässigkeit erfüllt werden.

In Abbildung 2-2 wird die integrierte Abhängigkeits Zuordnung für alle Server-und Anwendungs Verbindungen gezeigt, die von Azure Migrate ausgeführt werden.

![Positionieren von cloudinfrastrukturfähigen Anwendungen](./media/image2-2.png)

> **Abbildung 2–2.** Positionieren von cloudinfrastrukturfähigen Anwendungen

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Verwenden von Azure Site Recovery zum Migrieren Ihrer vorhandenen VMS zu Azure-VMS

Als Teil der End-to-End- [Azure migrate](https://aka.ms/azuremigrate)ist [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) ein Tool, mit dem Sie Ihre Web-Apps problemlos zu virtuellen Computern in Azure migrieren können. Sie können Site Recovery verwenden, um lokale VMS und physische Server in Azure zu replizieren oder um Sie an einen sekundären lokalen Standort zu replizieren. Sie können sogar eine Arbeitsauslastung, die auf einer unterstützten Azure-VM ausgeführt wird, auf einer lokalen *Hyper-V-* VM, auf einer *VMware* -VM oder auf einem physischen Windows-oder Linux-Server replizieren. Durch die Replikation in Azure entfallen die Kosten und die Komplexität der Verwaltung eines sekundären Rechenzentrums.

Site Recovery wird auch speziell für Hybrid Umgebungen, die teilweise lokal und teilweise in Azure sind, vorgenommen. Site Recovery können die Geschäftskontinuität sicherstellen, indem Sie Ihre apps, die auf virtuellen Computern ausgeführt werden, und lokale physische Server verfügbar halten, wenn ein Standort ausfällt. Es repliziert Workloads, die auf VMS und physischen Servern ausgeführt werden, damit Sie an einem sekundären Standort verfügbar bleiben, wenn der primäre Standort nicht verfügbar ist. Es werden Arbeits Auslastungen am primären Standort wieder hergestellt, wenn dieser wieder in Betrieb ist.

In Abbildung 2-3 wird die Ausführung mehrerer VM-Migrationen mithilfe Azure Site Recovery veranschaulicht.

![Positionieren von cloudinfrastrukturfähigen Anwendungen](./media/image2-3.png)

> **Abbildung 2-3.** Positionieren von cloudinfrastrukturfähigen Anwendungen

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Datenblatt "Azure migrate"**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure-Migrationscenter**

    <https://azure.microsoft.com/migration/>

- **Migrieren zu Azure mit Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Übersicht über Azure Site Recovery-Dienst**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migrieren von VMS in AWS zu Azure-VMS**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](migrate-your-relational-databases-to-azure.md)
