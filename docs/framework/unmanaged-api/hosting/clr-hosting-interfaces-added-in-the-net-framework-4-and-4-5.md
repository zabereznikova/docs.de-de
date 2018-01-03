---
title: "In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61231715a24978e7fe57b2c9e87e7968dc0fdbc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
Dieser Abschnitt beschreibt die Schnittstellen, die nicht verwaltete Hosts können Sie integrieren die common Language Runtime (CLR) in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], und höheren Versionen in ihre Anwendungen. Diese Schnittstellen bieten Methoden für einen Host zu konfigurieren und die Common Language Runtime in einen Prozess zu laden.  
  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], alle hosting Schnittstellen haben die folgenden Eigenschaften:  
  
-   Sie verwenden die Verwaltung der Objektlebensdauer (`AddRef` und `Release`), für die Kapselung (implizite Kontext) und `QueryInterface` aus COM  
  
-   Gibt es keine nicht-COM-Typen wie `BSTR`, `SAFEARRAY`, oder `VARIANT`.  
  
-   Es sind keine Modelle Apartment, Aggregation oder Registrierung die Aktivierung, mit denen die [CoCreateInstance-Funktion](http://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ICLRAppDomainResourceMonitor-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Enthält Methoden, die einer Anwendungsdomäne Arbeitsspeicher und CPU-Auslastung zu überprüfen.  
  
 [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Ermöglicht es dem Host den Anwendungsdomänen-Manager an, der die Standardanwendungsdomäne initialisiert werden, sowie an Initialisierungseigenschaften verwendet werden.  
  
 [ICLRGCManager2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) Methode, die einen Host für die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0 Werte größer als festzulegen ermöglicht `DWORD`.  
  
 [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 Enthält Methoden, die eine bestimmte Version der CLR zurückgeben, alle installierten clrs, Listen Sie alle in-Process-Laufzeiten, die Aktivierungsschnittstelle zurückgeben und ermitteln die CLR-Version verwendet, um eine Assembly zu kompilieren.  
  
 [ICLRMetaHostPolicy-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode, die eine CLR-Schnittstelle bereitstellt, anhand von Kriterien, die verwaltete Assembly, die Version und die Konfigurationsdatei.  
  
 [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Enthält Methoden, die Informationen zu einer bestimmten Laufzeit, einschließlich der Version, Verzeichnis und Auslastungsstatus zurückgeben.  
  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen an. Alle der [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) Methoden geben standard-COM-HRESULTs zurück.  
  
 [ICLRStrongName2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe des Secure Hash-Algorithmus (SHA-256, SHA-384 und SHA-512).  
  
 [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Stellt die Funktionalität von der [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); darüber hinaus bietet Methoden, die es ermöglichen, Thread-Abbrüche um für den aktuellen Thread verzögert werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Beschreibt die hosting-Schnittstellen mit den .NET Framework-Versionen 1.0 und 1.1 bereitgestellt.  
  
 [CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 Beschreibt die hosting-Schnittstellen mit den .NET Framework-Versionen 2.0, 3.0 und 3.5 bereitgestellt.  
  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 Führt die in .NET Framework-hosting.
