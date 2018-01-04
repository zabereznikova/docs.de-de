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
ms.workload: dotnet
ms.openlocfilehash: 3fa2eb347bc69a89545e6145154306f012e23490
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="instance-completion-action"></a>Instance Completion Action
Die **Instance Completion Action** -Eigenschaft des SQL-Workflowinstanzspeichers können Sie angeben, ob die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht wird, nachdem die Instanzen abgeschlossen wurden. Die zulässigen Werte für diese Eigenschaft sind **DeleteAll** und **DeleteNothing**. In der folgenden Liste werden diese Optionen beschrieben:  
  
-   **DeleteAll (Standard).** Wenn der Wert der Eigenschaft auf DeleteAll festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht, nachdem die Instanzen abgeschlossen wurden.  
  
-   **DeleteNothing.** Wenn der Wert der Eigenschaft auf DeleteNothing festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen in der Persistenzdatenbank beibehalten, nachdem die Instanzen abgeschlossen wurden.  
  
    > [!CAUTION]
    >  Das Beibehalten von Instanzzustandsinformationen nach dem Abschluss von Instanzen führt dazu, dass die Größe der Persistenzdatenbank zunimmt. Mit wachsender Größe der Datenbank dauern die Datenbankvorgänge, die das Persistenzsubsystem ausführt, immer länger. Deshalb müssen Sie die Instanzzustandsinformationen in regelmäßigen Abständen endgültig aus der Persistenzdatenbank löschen, damit die die Dienste Ihren Leistungsanforderungen entsprechend ausgeführt werden.
