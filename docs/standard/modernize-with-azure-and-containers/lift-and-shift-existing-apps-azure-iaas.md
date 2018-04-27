---
title: Heben Sie und verschieben Sie vorhandene apps Azure IaaS
description: Vorhandene .NET Anwendungen mit dem Azure-Cloud und Windows-Containern zu aktualisieren.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7922ad3a3cd5346f81008e1841a55b5e3663832
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="lift-and-shift-existing-apps-azure-iaas"></a>Heben Sie und verschieben Sie vorhandene apps Azure IaaS

> Vision: Geben Sie als ersten Schritt, reduzieren Ihre lokalen Investitionen und die Gesamtkosten der Hardware und Netzwerk während der automatischen Wartung einfach Ihre vorhandenen Anwendungen in der Cloud hosten.

Vor dem Abrufen in *wie* um Ihre vorhandenen Anwendungen auf Azure-Infrastruktur als Service (IaaS) Plattform zu migrieren, es ist wichtig, die Gründe analysieren *warum* Sie direkt zu IaaS migrieren möchten in Azure. Das Szenario auf diese Modernisierung Reifegrad ist im Wesentlichen mit virtuellen Computern in der Cloud, anstatt mit Ihrer aktuellen, lokale Infrastruktur zu verwenden.

Wird von einem anderen Punkt zu analysierenden *warum* möglicherweise in reinen statt einfach zu addieren, komplexere verwaltete Diensten in Azure IaaS-Cloud migrieren möchten. Sie müssen bestimmen, welche Fällen möglicherweise IaaS ursprünglich erfordern.

Abbildung 2: 1 positioniert Cloud-Infrastruktur einsatzfähige Anwendungen, in der Modernisierung Reifegrade:

![Positionieren von Cloud-Infrastruktur einsatzfähige Anwendungen](./media/image2-1.png)

> **Abbildung 2-1.** Positionieren von Cloud-Infrastruktur einsatzfähige Anwendungen

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Warum migrieren Sie vorhandene .NET-Webanwendungen auf Azure IaaS

Der Hauptgrund für die Migration in die Cloud, sogar auf eine anfängliche IaaS-Ebene ist, Reduzierung der Kosten zu erreichen. Mithilfe von weitere verwalteten Infrastrukturdiensten kann Ihrer Organisation ihre Investitionen in Hardware-Wartung, Server oder VM-Bereitstellung und Bereitstellung und infrastrukturverwaltung senken.

Nachdem Sie die Entscheidung für Ihre apps in die Cloud verschoben haben, wird die Hauptgründe dafür, warum Sie die Möglichkeit hätte IaaS anstelle von erweiterten Optionen wie PaaS einfach, die ist IaaS-Umgebung, mehr vertraut sein. Verschieben einer Umgebung, die Ihre aktuellen ähnelt, bietet lokalen Umgebung eine niedrigere Lernkurve, wodurch das besseren in die Cloud.

Allerdings bedeutet dauert besseren in die Cloud nicht, dass Sie den größten Nutzen, müssen Sie Ihre Anwendungen in der Cloud ausgeführt werden. Jedes Unternehmen werden die wichtigsten Vorteile von einer cloudmigration auf dem bereits eingeführt DevOps Cloudfähige und in PaaS (Cloudoptimiertes) Reifegrade erhalten.

Es ist auch deutlich geworden, dass Anwendungen sind einfacher zu aktualisieren und erneut in der Zukunft konzipiert werden, wenn diese bereits in der Cloud, sogar auf IaaS ausgeführt werden. Dies gilt teilweise da Datenmigration für die Anwendung bereits erreicht wurde. Darüber hinaus Ihrer Organisation erworben maßgeblichen Qualifikationen für die Arbeit in der Cloud, und gemacht, dass die Schicht Betrieb in einer "Cloud"Kultur.

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Wann zu IaaS statt nach PaaS migriert

In den nächsten Abschnitten erläutert Cloudfähige DevOps-Anwendungen, die größtenteils PaaS-Plattformen und Services basieren. Diese apps bieten Ihnen die meisten Vorteile in die Cloud migrieren.

Ermitteln Sie Ziel ist es einfach, bestehende Anwendungen in der Cloud zu verschieben, zuerst vorhandene Anwendungen, die erfordern beträchtliche Änderungen in Azure App Service ausgeführt. Diese apps sollte die erste Kandidaten sein.

Klicken Sie dann, wenn Sie nicht angezeigt werden sollen oder immer noch nicht auf Windows-Containern und oder Orchestrators wie Azure Service Fabric oder Kubernetes bewegen, ist noch, klicken Sie dann, wenn Sie einfache VMs (IaaS) verwenden würden.

Allerdings sollten Sie bedenken, dass ordnungsgemäß konfigurieren, Sichern und Verwalten von VMs deutlich mehr Zeit und IT-Kenntnisse, die im Vergleich zur Verwendung von PaaS-Dienste in Azure erforderlich ist. Wenn Sie virtuelle Computer in Azure in Betracht ziehen, stellen Sie sicher, dass Sie, die laufende Wartung leichter gepatcht berücksichtigen, aktualisieren und verwalten Ihre Umgebung mit virtuellen Computern. Virtuelle Computer in Azure ist IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Analysieren und migrieren Ihre vorhandenen Anwendungen in Azure verwenden Sie Azure migrieren

Migration zur Cloud muss nicht schwierig sein. Aber viele Organisationen für den abzurufenden umfassende in der Umgebung und die engen gegenseitigen Abhängigkeiten zwischen den Anwendungen, arbeitsauslastungen und Daten Einstieg - kämpfen. Ohne diese Sichtbarkeit kann es schwierig, Planen Sie den Pfad vorwärts sein. Ohne detaillierte Informationen auf, was für eine erfolgreiche Migration erforderlich ist haben nicht die richtigen Konversationen in Ihrer Organisation. Sie wissen nicht genug über das Potenzial Kostenvorteile, oder gibt an, ob arbeitsauslastungen konnte nur Lift und-Shift-erhebliche überarbeitet werden, um erfolgreich zu migrieren, müsste. Kein Wunder, dass viele Organisationen in jedem Fall.

[Azure migrieren](https://aka.ms/azuremigrate) ist ein neuer Dienst, der die Leitfäden, Einblicke und Mechanismen zur Unterstützung bei der Migration zu Azure erforderlich bereitstellt. Azure migrieren bietet:

- Ermittlung und Bewertung der lokalen virtuellen Computern

- Integrierte Abhängigkeit-Zuordnung für die vertrauenswürdige Ermittlung von Anwendungen mit mehreren Ebenen

- Intelligent Rightsizing auf virtuellen Azure-Computern

- Kompatibilität mit Richtlinien für das Wiederherstellen der potenziellen Probleme reporting

- Integration mit Azure-Datenbankverwaltungsdienst für die Ermittlung von Datenbanken und migration

Azure migrieren, können Sie sichergehen, die Ihre arbeitsauslastungen mit minimaler Auswirkung auf das Geschäft migrieren und wie erwartet in Azure ausgeführt werden können. Mit den richtigen Tools und Anleitungen erreichen Sie maximalen Rentabilität, kritische Leistung sicherzustellen und Zuverlässigkeit Anforderungen erfüllt sind.

Abbildung 2 x 2 zeigt Sie die integrierten Abhängigkeit-Zuordnung für alle Server und Anwendungen Verbindungen von Azure migrieren ausgeführt.

![Positionieren von Cloud-Infrastruktur einsatzfähige Anwendungen](./media/image2-2.png)

> **Abbildung 2 x 2.** Positionieren von Cloud-Infrastruktur einsatzfähige Anwendungen

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Verwenden Sie Azure Site Recovery, um Ihre vorhandenen virtuellen Computer zu Azure-VMs migrieren

Als Teil der End-to-End- [Azure migrieren](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) ist ein Tool, das Sie verwenden können, um Ihre Web-apps einfach zu virtuellen Computern in Azure zu migrieren. Sie können Site Recovery verwenden, können Sie einer lokalen virtuellen Computern und physischen Servern in Azure zu replizieren und sie auf einem sekundären lokalen Standort zu replizieren. Sie können auch eine arbeitsauslastung, die auf einer unterstützten Azure-VM auf einem lokalen läuft replizieren *Hyper-V* VM auf einem *VMware* VM, oder auf einem physischen Windows- oder Linux-Server. Die Replikation in Azure beseitigt die Kosten und Komplexität von einem sekundären Datencenter verwalten.

Site Recovery erfolgt auch speziell für hybridumgebungen, bei denen sind teilweise lokal und teilweise auf Azure. Site Recovery kann sichergestellt werden Geschäftskontinuität bleiben Ihre apps, die auf virtuellen Computern ausgeführt werden und lokalen physische Servern verfügbar, wenn ein Standort ausfällt. Repliziert Arbeitslasten, die auf virtuellen Computern und physischen Servern ausgeführt werden, damit sie verfügbar bleiben an einem sekundären Standort, wenn der primäre Standort nicht verfügbar ist. Er wird wiederhergestellt Arbeitslasten auf dem primären Standort, wenn es aktiv ist und erneut ausführen.

Abbildung 2 – 3 zeigt die Ausführung von mehreren VM-Migrationen mithilfe von Azure Site Recovery.

![Positionieren von Cloud-Infrastruktur einsatzfähige Anwendungen](./media/image2-3.png)

> **Abbildung 2 – 3.** Positionieren von Cloud-Infrastruktur einsatzfähige Anwendungen

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Datenblatt zu Azure migrieren**

    [https://aka.ms/azuremigration\_Datenblatt](https://aka.ms/azuremigration\_datasheet)

- **Azure migrieren**

    [http://azuremigrationcenter.com/](http://azuremigrationcenter.com/)

- **Migrieren Sie zu Azure Site Recovery**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

- **Azure Site Recovery-Dienst im Überblick**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

- **Migrieren von VMs in AWS auf Azure VMs**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
[Zurück](index.md)
[Weiter](migrate-your-relational-databases-to-azure.md)
