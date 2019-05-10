---
title: Instance Completion Action
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: d68f41a586e44f96c9ca26cf8a142a2782adaa36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662974"
---
# <a name="instance-completion-action"></a>Instance Completion Action
Die **Instance Completion Action** Eigenschaft von der SQL-Workflow-Instanz-Store ermöglicht die Angabe, ob die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht wird, nachdem die Instanzen abgeschlossen wurden. Die zulässigen Werte für diese Eigenschaft sind **DeleteAll** und **DeleteNothing**. In der folgenden Liste werden diese Optionen beschrieben:  
  
- **DeleteAll (Standard).** Wenn der Wert der Eigenschaft auf DeleteAll festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen aus der Persistenzdatenbank gelöscht, nachdem die Instanzen abgeschlossen wurden.  
  
- **DeleteNothing.** Wenn der Wert der Eigenschaft auf DeleteNothing festgelegt wird, werden die Daten und Metadaten von Workflowinstanzen in der Persistenzdatenbank beibehalten, nachdem die Instanzen abgeschlossen wurden.  
  
    > [!CAUTION]
    >  Das Beibehalten von Instanzzustandsinformationen nach dem Abschluss von Instanzen führt dazu, dass die Größe der Persistenzdatenbank zunimmt. Mit wachsender Größe der Datenbank dauern die Datenbankvorgänge, die das Persistenzsubsystem ausführt, immer länger. Deshalb müssen Sie die Instanzzustandsinformationen in regelmäßigen Abständen endgültig aus der Persistenzdatenbank löschen, damit die die Dienste Ihren Leistungsanforderungen entsprechend ausgeführt werden.
