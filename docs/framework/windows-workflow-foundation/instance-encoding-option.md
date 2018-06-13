---
title: Instance Encoding Option
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: cfe45428f546b6f47709c321099efdf7fbb25ef4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512537"
---
# <a name="instance-encoding-option"></a>Instance Encoding Option
Die **Instance Encoding Option** -Eigenschaft des SQL-Workflowinstanzspeichers können Sie angeben, ob die SQL-Persistenzanbieter die Zustandsinformationen zur Workflowinstanz mithilfe des GZip-Algorithmus vor dem Speichern komprimieren soll die die Informationen in die Persistenzdatenbank. Die zulässigen Werte für diese Eigenschaft sind: GZIP und None. Der Standardwert ist None. In der folgenden Liste werden diese Optionen beschrieben.  
  
1.  **GZip**. Der Persistenzanbieter codiert die Zustandsinformationen mithilfe des GZip-Algorithmus, bevor die Zustandsinformationen in der Persistenzdatenbank gespeichert werden.  
  
2.  **Keine**. Der Persistenzanbieter codiert die Zustandsinformationen nicht, bevor die Informationen in der Persistenzdatenbank gespeichert werden.  
  
 Durch die Codierung der Zustandsinformationen der Workflowinstanz mithilfe von GZip wird in der SQL-Datenbank weniger Speicher und Netzwerkkapazität belegt, wenn sich die Datenbank auf einem anderen Computer im Netzwerk befindet als der Host des Workflowdiensts. Allgemein empfiehlt es sich zum Festlegen der **Instance Encoding Option** Eigenschaft, um **keine** Wenn der workflowinstanzzustand klein ist.
