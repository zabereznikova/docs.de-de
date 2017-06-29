---
title: "Verwenden von Anwendungsdomänen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3aa6a381d7c6017e27deac642f23b68c50af7509
ms.contentlocale: de-de
ms.lasthandoff: 06/02/2017

---
# <a name="using-application-domains"></a>Verwenden von Anwendungsdomänen
Anwendungsdomänen stellen eine Isolationseinheit für die Common Language Runtime (CLR) bereit. Sie werden in einem Prozess erstellt und dort ausgeführt. Anwendungsdomänen werden normalerweise von einem Runtimehost erstellt. Dabei handelt es sich um eine Anwendung, die dafür verantwortlich ist, die Runtime in einen Prozess zu laden und Benutzercode innerhalb einer Anwendungsdomäne auszuführen. Der Runtimehost erstellt einen Prozess und eine Standardanwendungsdomäne und führt darin verwalteten Code aus. Runtimehosts sind z.B. ASP.NET, Microsoft Internet Explorer und Windows-Shell.  
  
 Für die meisten Anwendungen müssen Sie nicht Ihre eigene Anwendungsdomäne erstellen. Der Runtimehost erstellt alle erforderlichen Anwendungsdomänen für Sie. Sie können aber zusätzliche Anwendungsdomänen erstellen und konfigurieren, wenn Ihre Anwendung Code isolieren oder DLLs verwenden und entladen muss.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Erstellen einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Erläutert, wie Sie eine Anwendungsdomäne programmgesteuert erstellen  
  
 [Gewusst wie: Entladen einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Erläutert, wie Sie eine Anwendungsdomäne programmgesteuert entladen  
  
 [Gewusst wie: Konfigurieren einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Führt Sie in die Konfiguration einer Anwendungsdomäne ein  
  
 [Abrufen von Setupinformationen aus einer Anwendungsdomäne](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Erläutert, wie Sie Setupinformationen aus einer Anwendungsdomäne abrufen können  
  
 [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Erläutert wie Sie eine Assembly in eine Anwendungsdomäne laden können  
  
 [Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Erläutert, wie Sie Informationen zu einer Assembly abrufen können  
  
 [Erstellen von Schattenkopien von Assemblys](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Erläutert, wie Sie Assemblys mit Schattenkopien aktualisieren können, während diese gerade verwendet werden, und wie Sie Schattenkopien konfigurieren können  
  
 [Gewusst wie: Empfangen von Ausnahmebenachrichtigungen (erste Chance)](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Erläutert, wie Sie eine Benachrichtigung bezüglich einer ausgelösten Ausnahme abrufen können, bevor die CLR mit dem Suchen nach Ausnahmehandlern beginnt.  
  
 [Auflösen beim Laden von Assemblys](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Führt Sie in das Verwenden des Ereignisses <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> ein, um fehlgeschlagene Assemblyladevorgänge aufzulösen.  
  
## <a name="reference"></a>Verweis  
 <xref:System.AppDomain>  
 Stellt eine Anwendungsdomäne dar Bietet Methoden zum Erstellen und Steuern von Anwendungsdomänen  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Gibt einen Überblick über von Assemblys ausgeführte Funktionen  
  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.  
  
 [Ausgeben von dynamischen Methoden und Assemblys](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Beschreibt das Erstellen dynamischer Assemblys.  
  
 [Anwendungsdomänen](../../../docs/framework/app-domains/application-domains.md)  
 Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.  
  
 [Übersicht über Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.
