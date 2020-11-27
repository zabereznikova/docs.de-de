---
title: Hosting-Ausnahmen
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: 342420f10ed53e4f4786ed9506cfde5fbfcfc957
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263333"
---
# <a name="hosting-exceptions"></a>Hosting-Ausnahmen

In diesem Thema werden alle Ausnahmen aufgelistet, die durch Hosting generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Die vollständige URI ist nicht zulässig. Vollständige URIs sind für die ServiceHostingEnvironment.EnsureServiceAvailable API nicht zulässig. Verwenden Sie für den entsprechenden Dienst einen virtuellen Pfad.|  
|Hosting_BuildProviderCouldNotCreateType|Der angegebene CLR-Typ kann während der Kompilierung des Dienstes nicht geladen werden. Vergewissern Sie sich, dass dieser Typ entweder in einer Quelldatei definiert ist, die sich im Verzeichnis "\ App_Code der Anwendung" befindet \\ , das in einer kompilierten Assembly im Verzeichnis "\bin" der Anwendung enthalten ist \\ oder in einer im globalen Assemblycache installierten Assembly vorhanden ist. Bei dem Typnamen wird die Groß- und Kleinschreibung berücksichtigt. Die Verzeichnisse (z \\ . b. \ App_Code und \\ \bin) müssen sich im Stammverzeichnis der Anwendung befinden. Die \\ Verzeichnisse \ App_Code und \\ \bin können nicht in Unterverzeichnissen eingefügt werden.|
