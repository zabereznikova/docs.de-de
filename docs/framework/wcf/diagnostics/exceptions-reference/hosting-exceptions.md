---
title: "Hosting-Ausnahmen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Hosting-Ausnahmen
In diesem Thema werden alle Ausnahmen aufgelistet, die durch Hosting generiert werden.  
  
## Ausnahmeliste  
  
|Ressourcecode|Ressourcenzeichenfolge|  
|-------------------|----------------------------|  
|Hosting\_AddressIsAbsoluteUri|Die vollständige URI ist nicht zulässig.Vollständige URIs sind für die ServiceHostingEnvironment.EnsureServiceAvailable API nicht zulässig.Verwenden Sie für den entsprechenden Dienst einen virtuellen Pfad.|  
|Hosting\_BuildProviderCouldNotCreateType|Der angegebene CLR\-Typ kann während der Kompilierung des Dienstes nicht geladen werden.Stellen Sie sicher, dass dieser Typ entweder in einer Quelldatei im Verzeichnis \\\\App\_Code der Anwendung definiert ist, in einer kompilierten Assembly im Verzeichnis \\\\bin der Anwendung enthalten ist, oder in einer Assemly vorhanden ist, die im globalen Assemblycache installiert ist.Bei dem Typnamen wird die Groß\- und Kleinschreibung berücksichtigt.Die Verzeichnisse, wie \\\\App\_Code und \\\\bin, müssen sich im Stammverzeichnis der Anwendung befinden.Die Verzeichnisse \\\\App\_Code und \\\\bin können nicht in Unterverzeichnissen geschachtelt werden.|