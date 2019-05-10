---
title: In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96bc833915dd74756220b5e79a2866b41389dd45
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630509"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
In diesem Abschnitt wird beschrieben, Schnittstellen, die nicht verwaltete Hosts können Sie integrieren die common Language Runtime (CLR) in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], und höher in ihre Anwendungen. Diese Schnittstellen bieten Methoden, die für einen Host zu konfigurieren und die Runtime in einen Prozess geladen.  
  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], alle hosting Schnittstellen weisen folgende Merkmale auf:  
  
- Sie verwenden die Prozesslebensdauer-Verwaltung (`AddRef` und `Release`), Kapselung (implizite Context) und `QueryInterface` von COM.  
  
- Gibt es keine nicht-COM-Typen wie `BSTR`, `SAFEARRAY`, oder `VARIANT`.  
  
- Es gibt keine Apartmentmodells, Aggregation oder Registrierung, Aktivierung, mit denen die [CoCreateInstance-Funktion](https://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ICLRAppDomainResourceMonitor-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Bietet Methoden, die einer Anwendungsdomäne Arbeitsspeicher- und CPU-Auslastung zu überprüfen.  
  
 [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Ermöglicht dem Host an den Anwendungsdomänen-Manager, der zum Initialisieren von der Standardanwendungsdomäne, und klicken Sie zum Angeben von Eigenschaften zur datenquelleninitialisierung verwendet werden.  
  
 [ICLRGCManager2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode, die einen Host für die Größe der Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 Werte größer als festzulegen, kann `DWORD`.  
  
 [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 Enthält Methoden, die eine bestimmte Version der CLR zurückgeben, alle installierten clrs, Listen Sie alle in-Process-Laufzeiten, die Aktivierungsschnittstelle zurückgeben und ermitteln die CLR-Version verwendet, um eine Assembly kompilieren.  
  
 [ICLRMetaHostPolicy-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode, die eine CLR-Schnittstelle bereitstellt, anhand von Richtlinienkriterien, die verwaltete Assembly, die Version und die Konfigurationsdatei.  
  
 [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Bietet Methoden, die Informationen zu einer bestimmten Laufzeit, einschließlich Version, Verzeichnis und Ladestatus zurückgeben.  
  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Stellt grundlegende globale statische Funktionen für die Signierung von Assemblys mit starken Namen bereit. Alle der [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) -Methoden geben standard-COM-HRESULTs zurück.  
  
 [ICLRStrongName2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe der Hashalgorithmen (SHA-256, SHA-384 und SHA-512) sichern.  
  
 [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Bietet alle Funktionen des die [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); darüber hinaus bietet Methoden, mit denen Threadabbrüche um verzögert werden, für den aktuellen Thread.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Beschreibt die hosting-Schnittstellen mit den .NET Framework-Versionen 1.0 und 1.1 bereitgestellt.  
  
 [CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 Beschreibt die hosting-Schnittstellen mit den .NET Framework-Versionen 2.0, 3.0 und 3.5 bereitgestellt.  
  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 Führt die in .NET Framework-hosting.
