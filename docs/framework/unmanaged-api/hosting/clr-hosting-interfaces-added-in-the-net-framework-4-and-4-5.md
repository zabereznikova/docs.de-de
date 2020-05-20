---
title: In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: a524c0b0e01fbde95ce2341874511960b3e5738e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616852"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in den .NET Framework 4, .NET Framework 4,5 und höheren Versionen in Ihre Anwendungen integrieren können. Diese Schnittstellen bieten Methoden für einen Host zum Konfigurieren und Laden der Laufzeit in einen Prozess.  
  
 Beginnend mit dem .NET Framework 4 haben alle Hostingschnittstellen die folgenden Eigenschaften:  
  
- Sie verwenden die Lebensdauer Verwaltung ( `AddRef` und `Release` ), Kapselung (impliziter Kontext) und `QueryInterface` com.  
  
- Sie verwenden keine COM-Typen wie z `BSTR` `SAFEARRAY` . b., oder `VARIANT` .  
  
- Es gibt keine Apartment Modelle, Aggregationen oder Registrierungs Aktivierung, die die [cokreateinzustance-Funktion](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)verwenden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ICLRAppDomainResourceMonitor-Schnittstelle](iclrappdomainresourcemonitor-interface.md)  
 Stellt Methoden bereit, die den Arbeitsspeicher und die CPU-Auslastung einer Anwendungsdomäne überprüfen.  
  
 [ICLRDomainManager-Schnittstelle](iclrdomainmanager-interface.md)  
 Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.  
  
 [ICLRGCManager2-Schnittstelle](iclrgcmanager2-interface.md)  
 Stellt die [setgcstartuplimitsex](iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode bereit, die es einem Host ermöglicht, die Größe des Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte größer als festzulegen `DWORD` .  
  
 [ICLRMetaHost-Schnittstelle](iclrmetahost-interface.md)  
 Stellt Methoden bereit, die eine bestimmte Version der CLR zurückgeben, alle installierten clrs auflisten, alle in-Process-Runtimes auflisten, die Aktivierungs Schnittstelle zurückgeben und die CLR-Version ermitteln, die zum Kompilieren einer Assembly verwendet wird.  
  
 [ICLRMetaHostPolicy-Schnittstelle](iclrmetahostpolicy-interface.md)  
 Stellt die [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode bereit, die eine CLR-Schnittstelle basierend auf Richtlinien Kriterien, der verwalteten Assembly, der Version und der Konfigurationsdatei bereitstellt.  
  
 [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)  
 Stellt Methoden bereit, die Informationen zu einer bestimmten Laufzeit, einschließlich Version, Verzeichnis und Ladestatus, zurückgeben.  
  
 [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)  
 Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen bereit. Alle [ICLRStrongName](iclrstrongname-interface.md) -Methoden geben Standard-com-HRESULTs zurück.  
  
 [ICLRStrongName2-Schnittstelle](iclrstrongname2-interface.md)  
 Bietet die Möglichkeit, starke Namen mithilfe der SHA-2-Gruppe von sicheren Hash Algorithmen (SHA-256, SHA-384 und SHA-512) zu erstellen.  
  
 [ICLRTask2-Schnittstelle](iclrtask2-interface.md)  
 Stellt die gesamte Funktionalität der [ICLRTask-Schnittstelle](iclrtask-interface.md)bereit. Außerdem stellt Methoden bereit, mit denen Thread Abbrüche im aktuellen Thread verzögert werden können.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Beschreibt die Hostingschnittstellen, die mit den .NET Framework Versionen 1,0 und 1,1 bereitgestellt werden.  
  
 [CLR-Hostingschnittstellen](clr-hosting-interfaces.md)  
 Beschreibt die Hostingschnittstellen, die mit den .NET Framework Versionen 2,0, 3,0 und 3,5 bereitgestellt werden.  
  
 [Hosting](index.md)  
 Führt das Hosting in der .NET Framework ein.
