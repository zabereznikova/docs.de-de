---
title: Lift & shift von vorhandenen .NET apps zu Azure IaaS (bereit für Cloudinfrastruktur)
description: Modernisieren Sie vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern.
ms.date: 04/28/2018
ms.openlocfilehash: cda316ad01a58f26661395c804547de04e20d052
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758864"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Lift & shift von vorhandenen .NET apps zu Azure IaaS (bereit für Cloudinfrastruktur)

> Vision: Als ersten Schritt um Ihre lokalen Investitionen und die Gesamtkosten für Hardware und Wartung-Netzwerke zu reduzieren, einfach zum erneuten Hosten Sie Ihrer vorhandenen Anwendungen in der Cloud.

Vor dem Abrufen in *wie* um Ihre vorhandenen Anwendungen zu den Azure Infrastructure-as-a Service (IaaS)-Plattform migrieren, es ist wichtig, analysieren Sie die Gründe *warum* direkt zu IaaS migrieren möchten in Azure. Das Szenario auf diesem modernisierungsreifegrad ist im Grunde beim Einstieg in virtuellen Computern in der Cloud, anstatt Sie weiterhin Ihre aktuellen, eine lokale Infrastruktur zu verwenden.

Ist ein weiterer Aspekt, Analysieren *warum* in reines IaaS-Cloud statt einfach zu addieren, erweiterte verwaltete Diensten in Azure migrieren möchten. Bestimmen, welche Fällen möglicherweise IaaS im vornherein erfordern.

Abbildung 2-1 positioniert bereit für Cloudinfrastruktur-Anwendungen in die Modernisierung Reifegrads erforderlich:

![Positionieren bereit für Cloudinfrastruktur-Anwendungen](./media/image2-1.png)

> **Abbildung 2-1.** Positionieren bereit für Cloudinfrastruktur-Anwendungen

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Warum migrieren Sie vorhandener .NET Web-Anwendungen zu Azure IaaS

Der Hauptgrund für die Migration in die Cloud, sogar auf eine anfängliche IaaS-Ebene ist, um kosteneinsparungen zu erzielen. Mithilfe von weitere Dienste für verwaltete Infrastruktur, kann Ihre Organisation die Investitionen in Hardware-Wartung, Server oder VM-Bereitstellung und Bereitstellung und infrastrukturverwaltung senken.

Nachdem Sie die Entscheidung für Ihre apps in die Cloud verschoben haben, wird der Hauptgrund, warum Sie IaaS anstelle von erweiterten Optionen auswählen können wie PaaS einfach das ist die IaaS-Umgebung, besser vertraut sein. In einer Umgebung, die Ihre aktuellen ähnelt verschoben werden, bietet die lokale Umgebung eine niedrigere Lernkurve, dadurch wird es der schnellste Weg in die Cloud.

Allerdings bedeutet dauert der schnellste Weg in die Cloud nicht, dass Sie die größten Vorteile aus, wenn die Anwendungen, die in der Cloud ausgeführt werden. Jede Organisation werden die wichtigsten Vorteile von einer cloudmigration auf der bereits eingeführten Cloud optimiert und Native Cloud-Reifegrade erhalten.

Es ist auch offensichtlich geworden, dass Anwendungen sind einfacher zu modernisieren und in der Zukunft überarbeiten, wenn sie bereits in der Cloud, sogar in IaaS ausgeführt werden. Migration von Daten wurde bereits erreicht wurde. Darüber hinaus werden Ihre Organisation gewonnen Programmierkenntnisse erforderlich sind, für die Arbeit in der Cloud und die Verschiebung, die beim Betrieb in einem "Cloud-Culture" vorgenommen

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Zeitpunkt der Migration zu IaaS anstelle von zu PaaS

In den nächsten Abschnitten erläutern Cloudoptimierte Anwendungen, die hauptsächlich auf PaaS-Plattformen und Dienste basieren. Diese apps bieten Ihnen die meisten Vorteile von in die Cloud migrieren. 

Wenn das Ziel ist es einfach vorhandene Anwendungen in die Cloud verschieben, ermitteln Sie zuerst vorhandene Anwendungen, die erfordern keine wesentliche Änderungen in Azure App Service ausgeführt werden. Diese apps sollten die ersten Kandidaten für die Cloud optimiert. 

Anschließend kann nicht für die apps, die immer noch auf Windows-Container und PaaS verschieben, z. B. Migrieren App Service oder orchestratoren wie Azure Kubernetes Service diese einfache einfachen virtuellen Computern (IaaS). 

Allerdings sollten Sie bedenken, dass ordnungsgemäß konfigurieren, Sichern und Verwalten von VMs wesentlich mehr Zeit und IT-Kenntnisse, die im Vergleich zur Verwendung von PaaS-Dienste in Azure erforderlich sind. Wenn Sie Azure Virtual Machines in Betracht ziehen, stellen Sie sicher, dass Sie zu den Ständigen Wartungsaufwand zu patchen, aktualisieren und verwalten Ihre Umgebung mit virtuellen Computern berücksichtigen. Azure Virtual Machines ist IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Verwenden Sie Azure Migrate zum Analysieren und Ihre vorhandenen Anwendungen zu Azure migrieren

Migration in die Cloud nicht schwierig sein. Aber viele Organisationen, die niemand mehr Probleme, die ersten Schritte, um umfassende Einblicke in die Umgebung und eine enge Abhängigkeiten zwischen den Anwendungen, Workloads und Daten –. Ohne diese Sichtbarkeit kann es schwierig, Planen Sie die Lösung sein. Ohne ausführliche Informationen dazu, was für eine erfolgreiche Migration erforderlich sind haben nicht die richtigen Gespräche innerhalb Ihrer Organisation. Sie wissen nicht genug über die potenziellen kosteneinsparungen erzielen, oder gibt an, ob Workloads nur per Lift & Shift können, oder für eine erfolgreiche Migration Überarbeitung ist erforderlich. Kein Wunder, dass viele Organisationen zögern.

[Azure Migrate](https://aka.ms/azuremigrate) ist ein neuer Dienst, der die Anleitung, Einblicke und Mechanismen erforderlich, um Sie bei der Migration zu Azure bereitstellt. Azure Migrate bietet:

- Ermittlung und Bewertung für lokale virtuelle Computer

- Integrierte abhängigkeitszuordnung für die zuverlässige-Ermittlung von Anwendungen mit mehreren Ebenen

- Intelligente die richtige Bemessung auf Azure Virtual machines

- Kompatibilität mit Richtlinien für die Behebung potenzieller Probleme

- Integration in Azure-Datenbank-Management-Dienst für die Ermittlung von Datenbanken und migration

Azure Migrate bietet Ihnen vertrauen, die Ihre Workloads mit minimalen Auswirkungen auf das Unternehmen migrieren und wie erwartet in Azure ausgeführt werden können. Mit den richtigen Tools und Anleitungen erreichen Sie maximale Rendite, kritische Leistung sicherzustellen, und Zuverlässigkeit Anforderungen erfüllt sind.

Abbildung 2-2: erfahren Sie, die integrierte Dependency-Zuordnung für alle Server und Anwendungen Verbindungen, die von Azure Migrate ausgeführt wird.

![Positionieren bereit für Cloudinfrastruktur-Anwendungen](./media/image2-2.png)

> **Abbildung 2-2.** Positionieren bereit für Cloudinfrastruktur-Anwendungen

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Verwenden von Azure Site Recovery zum Migrieren von Ihrer vorhandenen VMs zu Azure-VMs

Als Teil der End-to-End [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) ist ein Tool, das Sie verwenden können, um Ihre Web-apps ganz einfach mit virtuellen Computern in Azure zu migrieren. Sie können Site Recovery zum Replizieren von lokalen VMs und physischen Servern in Azure oder an einem sekundären lokalen Ort replizieren. Sie können sogar replizieren, eine arbeitsauslastung, die auf eine unterstützte Azure-VM auf einem lokalen ausgeführt wird *Hyper-V* VM auf einen *VMware* virtuellen Computer oder auf einem physischen Server für Windows oder Linux. Replikation in Azure entfallen die Kosten und Komplexität der Verwaltung eines sekundären Datencenters.

Site Recovery erfolgt auch speziell für hybridumgebungen, die teilweise lokal und teilweise in Azure. Site Recovery unterstützt die Gewährleistung von Geschäftskontinuität durch, halten Ihre apps, die auf virtuellen Computern ausgeführt werden und auf lokalen physische Servern verfügbar, wenn ein Standort ausfällt. Repliziert Workloads, die auf virtuellen Computern und physischen Servern ausgeführt werden, sodass sie verfügbar an einem sekundären Standort bleiben, wenn der primäre Standort nicht verfügbar ist. Es wird die Wiederherstellung Workloads in der primäre Standort wieder betriebsbereit ist und erneut ausführen.

Abbildung 2 – 3 zeigt die Ausführung von mehreren VM-Migrationen mithilfe von Azure Site Recovery.

![Positionieren bereit für Cloudinfrastruktur-Anwendungen](./media/image2-3.png)

> **Abbildung 2 – 3.** Positionieren bereit für Cloudinfrastruktur-Anwendungen

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Datenblatt zu Azure migrieren**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure-Migrationscenter**

    <https://azure.microsoft.com/migration/>

- **Migrieren Sie zu Azure mit Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Übersicht über Azure Site Recovery-Dienst**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migrieren von VMs in AWS zu Azure-VMs**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](migrate-your-relational-databases-to-azure.md)
