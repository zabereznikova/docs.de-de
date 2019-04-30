---
title: Instance Encoding Option
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: c4de7c45d899f45a7b5b71d563257d9accb8fdbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928711"
---
# <a name="instance-encoding-option"></a>Instance Encoding Option
Die **Instance Encoding Option** Eigenschaft von der SQL-Workflow-Instanz-Store ermöglicht die Angabe, ob der SQL-Persistenzanbieter die Zustandsinformationen zur Workflowinstanz mithilfe des GZip-Algorithmus vor dem Speichern komprimiert werden soll, die die Informationen in der Persistenzdatenbank gespeichert. Die zulässigen Werte für diese Eigenschaft sind: GZip und None. Der Standardwert ist None. In der folgenden Liste werden diese Optionen beschrieben.  
  
1. **GZip**. Der Persistenzanbieter codiert die Zustandsinformationen mithilfe des GZip-Algorithmus, bevor die Zustandsinformationen in der Persistenzdatenbank gespeichert werden.  
  
2. **Keine**. Der Persistenzanbieter codiert die Zustandsinformationen nicht, bevor die Informationen in der Persistenzdatenbank gespeichert werden.  
  
 Durch die Codierung der Zustandsinformationen der Workflowinstanz mithilfe von GZip wird in der SQL-Datenbank weniger Speicher und Netzwerkkapazität belegt, wenn sich die Datenbank auf einem anderen Computer im Netzwerk befindet als der Host des Workflowdiensts. Allgemein empfiehlt es sich um legen Sie die **Instance Encoding Option** Eigenschaft **keine** Wenn der workflowinstanzzustand klein ist.
