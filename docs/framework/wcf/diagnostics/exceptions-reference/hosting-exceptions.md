---
title: Hosting-Ausnahmen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b296578efb6eb9b1e6372dbad647fdea22dbaddf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-exceptions"></a>Hosting-Ausnahmen
In diesem Thema werden alle Ausnahmen aufgelistet, die durch Hosting generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Die vollständige URI ist nicht zulässig. Vollständige URIs sind für die ServiceHostingEnvironment.EnsureServiceAvailable API nicht zulässig. Verwenden Sie für den entsprechenden Dienst einen virtuellen Pfad.|  
|Hosting_BuildProviderCouldNotCreateType|Der angegebene CLR-Typ kann während der Kompilierung des Dienstes nicht geladen werden. Stellen Sie sicher, dass dieser Typ entweder in einer Quelldatei befindet sich in der Anwendungsverzeichnis definiert ist \\im Verzeichnis \App_Code, in einer kompilierten Assembly in der Anwendungsverzeichnis enthaltenen \\\bin Verzeichnis oder in einer Assembly im installierten vorhanden der Globaler Assemblycache. Bei dem Typnamen wird die Groß- und Kleinschreibung berücksichtigt. Die Verzeichnisse, z. B. \\\App_Code und \\\bin muss in das Stammverzeichnis der Anwendung befinden. Die \\\App_Code und \\\bin Verzeichnisse können nicht in Unterverzeichnissen geschachtelt werden.|
