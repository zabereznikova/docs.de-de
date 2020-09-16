---
title: Übersicht über die analytische Ablaufverfolgung
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: b519156faba68c769f4c1380a11706aebaab7e7c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559056"
---
# <a name="analytic-tracing-overview"></a>Übersicht über analytische Ablauf Verfolgung

Die analytische Ablaufverfolgung in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] ist eine Ablaufverfolgungsfunktion mit hoher Leistung und geringer Ausführlichkeit, die auf ETW (Ereignisablaufverfolgung für Windows) aufbaut. ETW wird auf Kernelebene ausgeführt, um den Mehraufwand durch Ablaufverfolgungsvorgänge so weit wie möglich zu reduzieren. Dabei werden Benutzer- und Kernelmodusereignisse auf effiziente Weise gepuffert, und das dynamische Aktivieren ist ohne Neustarts des Diensts möglich. Die Ablaufverfolgungsdaten sind in den Ereignisprotokollen verfügbar, nachdem sie ausgegeben und empfangen wurden.

Weitere Informationen zu etw finden Sie unter verbessertes [Debugging und Leistungsoptimierung mit etw](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).

 Zusätzlich zur Verwendung der Windows-System-, Sicherheits-und Anwendungs Ereignisprotokolle zur Analyse der Anwendung wurden in Windows Vista und Windows Server 2008 weitere Protokolle unter dem Knoten der obersten Ebene der Anwendungs-und Dienst Protokolle eingeführt. Der Zweck dieser neuen Protokolle ist das Speichern von Ereignissen für eine bestimmte Anwendung oder eine bestimmte Komponente anstelle von globalen Ereignissen, die systemweite Auswirkungen haben (z. B. der Typ von Ereignissen, die das Sicherheitsereignisprotokoll ggf. aufzeichnet). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] vereinheitlicht und korreliert die Protokollierung von WCF-Ablauf Verfolgungs Ereignissen, WCF-Nachrichten Protokollen und- [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] nach Verfolgungs Datensätzen mit den Anwendungs-und Dienst Protokollen.

In den folgenden Abschnitten werden Konzepte und Funktionen behandelt, die für die analytische WCF-Ablauf Verfolgung gelten.

## <a name="enable-wcf-diagnostics-settings"></a>WCF-Diagnose Einstellungen aktivieren

Die WCF-Diagnose ist im `<system.serviceModel><diagnostics>` Konfigurations Abschnitt aktiviert.

```xml
<system.serviceModel>
  <diagnostics>
```

Die WCF-Diagnose Einstellungen für eine im Web gehostete virtuelle IIS-Anwendung werden in der *Web.config* -Datei aktiviert. Eine andere Möglichkeit besteht darin, eine *Web.config* -Datei in einem Unterverzeichnis innerhalb der Anwendung zu erstellen. Mit dieser Auswahl werden die Einstellungen auf alle Dienste innerhalb eines Unterverzeichnisses angewendet. Um sicherzustellen, dass die Diagnose Einstellungen für alle Dienste innerhalb der Anwendung konsistent initialisiert werden, sollten sich die Einstellungen in der *Web.config* -Datei im Anwendungsverzeichnis und nicht in einem der einzelnen Unterverzeichnisse innerhalb der Anwendung befinden.

## <a name="channels"></a>Channels

ETW ermöglicht Softwarekomponenten mithilfe von Kanälen (Channels) das direkte Weiterleiten von Ereignissen an eine bestimmte Zielgruppe. Beispielsweise können Sie Ereignisse für Systemadministratoren an einen Kanal und Ereignisse, die für Anwendungsentwickler wichtig sind, an einen anderen Kanal senden. Kanäle werden mit Windows benannt und registriert, damit Consumer die Ereignisse eines Kanals mithilfe Ereignisanzeige anzeigen können.

 Die analytische Ablauf Verfolgungs Funktion für WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] schreibt in den Kanal Microsoft-Windows-Application-Server-Applications. Dieser Kanal wurde für Benutzer entwickelt, die die Integrität der WCF-Dienste in der Produktionsumgebung überwachen möchten. Es definiert einen kleinen Satz von Ereignissen, der in vielen Integritäts Überwachungs-und Problem Behandlungs Szenarios verwendet werden kann.

 Um Ereignisablaufverfolgung für ein Windows-Manifest zu aktivieren, damit Meldungen im Ereignisprotokoll ordnungsgemäß decodiert werden, verwenden Sie in der Befehlszeile das ServiceModelReg-Tool wie folgt:

 `ServiceModelReg.exe -i -c:etw`

## <a name="dynamic-configuration"></a>Dynamische Konfiguration

Die ETW-Infrastruktur ermöglicht das dynamische Aktivieren und Konfigurieren der Ablaufverfolgung mit Windows-Standardtools. Weitere Informationen finden Sie unter [dynamisches Aktivieren der analytischen Ablauf Verfolgung](dynamically-enabling-analytic-tracing.md).

## <a name="message-flow-tracing"></a>Ablaufverfolgung des Nachrichtenflusses

Weitere Informationen zum Aktivieren der Ablauf Verfolgung für den Nachrichtenfluss finden Sie unter [Konfigurieren der Ablauf Verfolgung für den Nachrichtenfluss](configuring-message-flow-tracing.md).

## <a name="keywords"></a>Keywords

Schlüsselwörter werden verwendet, um Ablauf Verfolgungs Meldungen zu filtern und zu definieren, welche Komponente des .NET Framework das Ereignis ausgegeben hat. Weitere Informationen finden Sie unter [dynamisches Aktivieren der analytischen Ablauf Verfolgung](dynamically-enabling-analytic-tracing.md).
