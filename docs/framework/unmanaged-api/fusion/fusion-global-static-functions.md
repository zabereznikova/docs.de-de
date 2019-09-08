---
title: Fusion – Globale statistische Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a8f15bc862c0486311960f7567c49424859846e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795313"
---
# <a name="fusion-global-static-functions"></a>Fusion – Globale statistische Funktionen
In diesem Abschnitt werden die nicht verwalteten globalen statischen Funktionen beschrieben, die von der Fusion-API verwendet werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ClearDownloadCache-Funktion](cleardownloadcache-function.md)  
 Löscht den globalen Assemblycache der heruntergeladenen Assemblys.  
  
 [CompareAssemblyIdentity-Funktion](compareassemblyidentity-function.md)  
 Vergleicht zwei Assemblyidentitäten, um zu bestimmen, ob Sie äquivalent sind.  
  
 [CreateApplicationContext-Funktion](createapplicationcontext-function.md)  
 Nur intern. (Diese Funktion unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [CreateAssemblyCache-Funktion](createassemblycache-function.md)  
 Ruft einen Zeiger auf eine neue [IAssemblyCache](iassemblycache-interface.md) -Instanz ab, die den globalen Assemblycache darstellt.  
  
 [CreateAssemblyEnum-Funktion](createassemblyenum-function.md)  
 Ruft einen Zeiger auf eine [IAssemblyEnum](iassemblyenum-interface.md) -Instanz ab, die eine Liste von-Objekten darstellt, die in der angegebenen Assembly vorhanden sind.  
  
 [CreateAssemblyNameObject-Funktion](createassemblynameobject-function.md)  
 Ruft einen Zeiger auf eine [IAssemblyName](iassemblyname-interface.md) -Instanz ab, die die eindeutige Identität der Assembly mit dem angegebenen Namen darstellt.  
  
 [CreateHistoryReader-Funktion](createhistoryreader-function.md)  
 Erstellt einen Verlaufs Leser für die angegebene Datei.  
  
 [CreateInstallReferenceEnum-Funktion](createinstallreferenceenum-function.md)  
 Ruft einen Zeiger auf eine [IInstallReferenceEnum](iinstallreferenceenum-interface.md) -Instanz ab, die eine Liste der Verweise einer Anwendung auf die angegebene Assembly darstellt.  
  
 [GetAppIdAuthority-Funktion](getappidauthority-function.md)  
 Ruft einen Zeiger auf eine [IAppIdAuthority](iappidauthority-interface.md) -Instanz ab, die Schlüssel für Anwendungs Identitäten und-Verweise verwaltet.  
  
 [GetAssemblyIdentityFromFile-Funktion](getassemblyidentityfromfile-function.md)  
 Ruft einen Zeiger auf ein `IUnknown` -Objekt mit dem `IID` angegebenen in der Assembly am angegebenen Dateipfad ab.  
  
 [GetCachePath-Funktion](getcachepath-function.md)  
 Ruft den Pfad zur zwischengespeicherten Assembly unter Verwendung der angegebenen Flags ab.  
  
 [GetHistoryFileDirectory-Funktion](gethistoryfiledirectory-function.md)  
 Ruft den Pfad des Verzeichnisses für den Anwendungs Verlauf ab.  
  
 [GetIdentityAuthority-Funktion](getidentityauthority-function.md)  
 Ruft einen Zeiger auf eine [IIdentityAuthority](iidentityauthority-interface.md) -Instanz ab, die Schlüssel für Code Objekte verwaltet.  
  
 [IsFrameworkAssembly-Funktion](isframeworkassembly-function.md)  
 Ruft einen Wert ab, der angibt, ob die angegebene Assembly verwaltet wird.  
  
 [NukeDownloadedCache-Funktion](nukedownloadedcache-function.md)  
 Löscht den Common Language Runtime Download Cache.  
  
 [PreBindAssemblyEx-Funktion](prebindassemblyex-function.md)  
 Ruft den anzeigen Amen für eine Assembly nach der Richtlinie ab.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Fusion-Schnittstellen](fusion-interfaces.md)  
  
 [Fusion-Enumerationen](fusion-enumerations.md)  
  
 [Fusion-Strukturen](fusion-structures.md)  
  
 [Globaler Assemblycache](../../app-domains/gac.md)
