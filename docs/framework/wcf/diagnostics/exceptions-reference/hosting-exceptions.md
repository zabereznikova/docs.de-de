---
title: Hosting-Ausnahmen
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934731"
---
# <a name="hosting-exceptions"></a>Hosting-Ausnahmen
In diesem Thema werden alle Ausnahmen aufgelistet, die durch Hosting generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Die vollständige URI ist nicht zulässig. Vollständige URIs sind für die ServiceHostingEnvironment.EnsureServiceAvailable API nicht zulässig. Verwenden Sie für den entsprechenden Dienst einen virtuellen Pfad.|  
|Hosting_BuildProviderCouldNotCreateType|Der angegebene CLR-Typ kann während der Kompilierung des Dienstes nicht geladen werden. Stellen Sie sicher, dass dieser Typ entweder in einer Quelldatei befindet sich in der Anwendung definiert ist \\Verzeichnis \App_Code, in einer kompilierten Assembly befindet sich in der Anwendung enthaltenen \\\bin Verzeichnis oder in einer Assembly im installierten vorhanden der Globaler Assemblycache. Bei dem Typnamen wird die Groß- und Kleinschreibung berücksichtigt. Die Verzeichnisse wie z. B. \\\App_Code und \\\bin muss sich im Stammverzeichnis der Anwendung befinden. Die \\\App_Code und \\\bin Verzeichnisse können nicht in Unterverzeichnissen geschachtelt werden.|
