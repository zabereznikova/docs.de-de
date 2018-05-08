---
title: Hosting-Ausnahmen
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-exceptions"></a>Hosting-Ausnahmen
In diesem Thema werden alle Ausnahmen aufgelistet, die durch Hosting generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Die vollständige URI ist nicht zulässig. Vollständige URIs sind für die ServiceHostingEnvironment.EnsureServiceAvailable API nicht zulässig. Verwenden Sie für den entsprechenden Dienst einen virtuellen Pfad.|  
|Hosting_BuildProviderCouldNotCreateType|Der angegebene CLR-Typ kann während der Kompilierung des Dienstes nicht geladen werden. Stellen Sie sicher, dass dieser Typ entweder in einer Quelldatei befindet sich in der Anwendungsverzeichnis definiert ist \\im Verzeichnis \App_Code, in einer kompilierten Assembly in der Anwendungsverzeichnis enthaltenen \\\bin Verzeichnis oder in einer Assembly im installierten vorhanden der Globaler Assemblycache. Bei dem Typnamen wird die Groß- und Kleinschreibung berücksichtigt. Die Verzeichnisse, z. B. \\\App_Code und \\\bin muss in das Stammverzeichnis der Anwendung befinden. Die \\\App_Code und \\\bin Verzeichnisse können nicht in Unterverzeichnissen geschachtelt werden.|
