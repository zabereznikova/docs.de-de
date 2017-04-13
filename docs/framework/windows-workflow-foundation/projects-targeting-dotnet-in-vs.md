---
title: "Erstellen von Projekten f&#252;r .NET Framework 3.0 und 3.5 in Visual Studio 2010 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Erstellen von Projekten f&#252;r .NET Framework 3.0 und 3.5 in Visual Studio 2010
Mit [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] können Sie Projekte für [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], Version 3.0 oder 3.5, erstellen.In diesem Thema wird die dafür erforderliche Vorgehensweise beschrieben.  
  
> [!NOTE]
>  Stellen Sie beim Hinzufügen von Aktivitäten sicher, dass die erforderliche Version von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] festgelegt wurde.Wenn Sie die Zielversion des Workflows ändern, nachdem die Aktivitäten hinzugefügt wurden, kann der Workflow nicht überprüft werden.  
  
> [!WARNING]
>  Wenn Sie einen bestehenden Workflow mit .NET Framework 3.5\-Aktivitäten in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] öffnen, wird ein Fehler bei `this.SetValue()` verursacht.Um Projekte zu öffnen, die mit früheren Versionen von .NET Framework erstellt wurden, öffnen Sie zunächst einen leeren Workflow im Designer, und fügen Sie eine .NET Framework 3.5\-Aktivität hinzu.  
  
## So erstellen Sie ein .NET Framework 3.0\- oder 3.5\-Projekt mit Visual Studio 2010  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **Neu** und **Projekt** aus.  
  
3.  Wählen Sie in der Dropdownliste oben im Dialogfeld die gewünschte Version von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] aus.  
  
## So aktualisieren Sie die Zielversion von .NET Framework  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie in der Dropdownliste **Zielframework** die gewünschte Version aus.