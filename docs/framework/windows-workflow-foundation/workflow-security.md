---
title: Workflowsicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: 6253a0d76d8b1db938e789f19d2cdd5abba9b700
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273892"
---
# <a name="workflow-security"></a>Workflowsicherheit

Windows Workflow Foundation (WF) ist in verschiedene Technologien integriert, z. b. Microsoft SQL Server und Windows Communication Foundation (WCF). Die Interaktion mit diesen Technologien kann zu Sicherheitsproblemen für den Workflow führen, falls diese nicht ordnungsgemäß durchgeführt wird.

## <a name="persistence-security-concerns"></a>Sicherheitsaspekte der Persistenz

1. Workflows, die eine <xref:System.Activities.Statements.Delay>-Aktivität und Persistenz verwenden, müssen von einem Dienst erneut aktiviert werden. Windows AppFabric verwendet den Workflowverwaltungsdienst (WMS), um Workflows mit abgelaufenen Zeitgebern erneut zu aktivieren. WMS erstellt einen <xref:System.ServiceModel.WorkflowServiceHost> zum Hosten des erneut aktivierten Workflows. Wenn der WMS-Dienst beendet wird, werden beibehaltene Workflows nicht erneut aktiviert, wenn deren Timer ablaufen.

2. Die permanente Instanziierung sollte vor dem Zugriff durch böswillige Entitäten außerhalb der Anwendungsdomäne geschützt werden. Darüber hinaus sollten Entwickler sicherstellen, dass schädlicher Code nicht in derselben Anwendungsdomäne wie der Code für die permanente Instanziierung ausgeführt werden kann.

3. Die permanente Instanziierung sollte nicht mit erweiterten Berechtigungen (Administrator) ausgeführt werden.

4. Die Daten, die außerhalb der Anwendungsdomäne verarbeitet werden, sollten geschützt werden.

5. Anwendungen, die eine Sicherheitsisolation erfordern, sollten nicht dieselbe Instanz wie die Schemaabstraktion verwenden. Derartige Anwendungen sollten verschiedene Speicheranbieter oder Speicheranbieter verwenden, die für die Verwendung unterschiedlicher Speicherinstanziierungen konfiguriert wurden.

## <a name="sql-server-security-concerns"></a>SQL Server-Sicherheitsaspekte

- Wenn eine hohe Zahl an untergeordneten Aktivitäten, Speicherorten, Lesezeichen, Hosterweiterungen oder Bereichen verwendet wird oder wenn Lesezeichen mit sehr großen Nutzlasten verwendet werden, kann es zu einer Überlastung des Arbeitsspeichers kommen. Außerdem kann während des Persistenzvorgangs eine unangemessen hohe Menge an Datenbankspeicherplatz zugeordnet werden. Sie können dieses Risiko reduzieren, indem Sie die Sicherheit auf Objekt- und Datenbankebene verwenden.

- Bei der Verwendung von <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> muss der Instanzspeicher gesichert werden.

- Vertrauliche Daten im Instanzspeicher sollten verschlüsselt werden. Weitere Informationen finden Sie unter [SQL Server Encryption](/sql/relational-databases/security/encryption/sql-server-encryption).

- Da die Datenbank-Verbindungszeichenfolge häufig in einer Konfigurationsdatei enthalten ist, sollte Sicherheit auf Windows-Ebene (ACL) verwendet werden, um sicherzustellen, dass die Konfigurationsdatei (normalerweise "Web.Config") sicher ist und dass keine Anmelde- und Kennwortdaten in der Verbindungszeichenfolge enthalten sind. Die Windows-Authentifizierung sollte stattdessen zwischen der Datenbank und dem Webserver verwendet werden.

## <a name="considerations-for-workflowservicehost"></a>Überlegungen zu WorkflowServiceHost

- Windows Communication Foundation (WCF)-Endpunkte, die in Workflows verwendet werden, sollten gesichert werden. Weitere Informationen finden Sie unter [Übersicht über die WCF-Sicherheit](../wcf/feature-details/security-overview.md).

- Sie können die Autorisierung auf Hostebene mit <xref:System.ServiceModel.ServiceAuthorizationManager> implementieren. Weitere Informationen finden [Sie unter Gewusst wie: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md) .

- Der ServiceSecurityContext für die eingehende Nachricht ist über den Zugriff auf OperationContext auch im Workflow verfügbar.

## <a name="wf-security-pack-ctp"></a>WF-Sicherheitspaket CTP

 Das Microsoft WF Security Pack Community Technology Preview (CTP) 1 ist ein Satz von Aktivitäten und deren Implementierung auf der Grundlage von [Windows Workflow Foundation](index.md) in [.NET Framework 4](/previous-versions/dotnet/netframework-4.0/w0x726c2(v=vs.100)) (WF 4) und [Windows Identity Foundation (WIF)](/previous-versions/dotnet/framework/security/index). Das Microsoft WF-Sicherheitspaket CTP 1 enthält beide Aktivitäten und deren Designer, die veranschaulichen, wie einfach verschiedene sicherheitsrelevante Szenarien mithilfe von Workflows aktiviert werden können, darunter:

1. Wechseln zu einer Clientidentität im Workflow

2. Workflowinterne Autorisierung, z. B. PrincipalPermission und Validierung von Ansprüchen

3. Authentifiziertes Messaging mit im Workflow angegebenen ClientCredentials, z. B. Benutzername/Kennwort oder ein Token, das von einem Sicherheitstokendienst (STS) abgerufen wurde

4. Übertragen eines Clientsicherheitstokens an einen Back-End-Dienst (anspruchsbasierte Delegierung) mithilfe von WS-Trust ActAs

Weitere Informationen und das Herunterladen des WF Security Pack CTP finden Sie unter: [WF Security Pack CTP](https://archive.codeplex.com/?p=wf)
