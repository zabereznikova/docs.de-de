---
title: Instance Encoding Option
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 416394eb346a7c82385da32a89bd54179b255cd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279895"
---
# <a name="instance-encoding-option"></a>Instance Encoding Option

Mit der Eigenschaft **instance Encoding Option** des SQL-workflowinstanzspeichers können Sie angeben, ob der SQL-Persistenzanbieter die Zustandsinformationen der Workflow Instanz mithilfe des gzip-Algorithmus komprimieren soll, bevor die Informationen in der Persistenzdatenbank gespeichert Die zulässigen Werte für diese Eigenschaft sind: GZIP und None. Der Standardwert lautet „Keine“. In der folgenden Liste werden diese Optionen beschrieben.  
  
1. **Gzip**. Der Persistenzanbieter codiert die Zustandsinformationen mithilfe des GZip-Algorithmus, bevor die Zustandsinformationen in der Persistenzdatenbank gespeichert werden.  
  
2. **None** (Keine). Der Persistenzanbieter codiert die Zustandsinformationen nicht, bevor die Informationen in der Persistenzdatenbank gespeichert werden.  
  
 Durch die Codierung der Zustandsinformationen der Workflowinstanz mithilfe von GZip wird in der SQL-Datenbank weniger Speicher und Netzwerkkapazität belegt, wenn sich die Datenbank auf einem anderen Computer im Netzwerk befindet als der Host des Workflowdiensts. Eine allgemeine Anleitung besteht darin, die Eigenschaft **instance Encoding Option** auf **None** festzulegen, wenn der Zustand der workflowinstanzinstanz gering ist.
