---
title: Instance Completion Action
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 83dec7ef4c911c0bca94caf7cc4c4bf832c8e1b6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="instance-completion-action"></a>Instance Completion Action
Die **Instance Completion Action** -Eigenschaft des SQL-Workflowinstanzspeichers können Sie angeben, ob die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht wird, nachdem die Instanzen abgeschlossen wurden. Die zulässigen Werte für diese Eigenschaft sind **DeleteAll** und **DeleteNothing**. In der folgenden Liste werden diese Optionen beschrieben:  
  
-   **DeleteAll (Standard).** Wenn der Wert der Eigenschaft auf DeleteAll festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht, nachdem die Instanzen abgeschlossen wurden.  
  
-   **DeleteNothing.** Wenn der Wert der Eigenschaft auf DeleteNothing festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen in der Persistenzdatenbank beibehalten, nachdem die Instanzen abgeschlossen wurden.  
  
    > [!CAUTION]
    >  Das Beibehalten von Instanzzustandsinformationen nach dem Abschluss von Instanzen führt dazu, dass die Größe der Persistenzdatenbank zunimmt. Mit wachsender Größe der Datenbank dauern die Datenbankvorgänge, die das Persistenzsubsystem ausführt, immer länger. Deshalb müssen Sie die Instanzzustandsinformationen in regelmäßigen Abständen endgültig aus der Persistenzdatenbank löschen, damit die die Dienste Ihren Leistungsanforderungen entsprechend ausgeführt werden.
