---
title: "Verwenden einer benutzerdefinierten Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7558ca965af6cc9acd35ecab47bf9f66f592b15f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-custom-activity"></a>Verwenden einer benutzerdefinierten Aktivität
Aktivitäten, die von <xref:System.Activities.Activity> oder den Unterklassen abgeleitet werden, können zu größeren Workflows zusammengesetzt oder direkt im Code erstellt werden. In diesem Thema wird beschrieben, wie Sie benutzerdefinierte Aktivitäten in Workflows verwenden, die entweder im Code oder im Designer erstellt wurden.  
  
> [!NOTE]
>  Benutzerdefinierte Aktivitäten können im selben Projekt, in dem sie definiert sind, verwendet werden, solange die benutzerdefinierte Aktivität und der Aktivität, die verwendet werden (d. h. von einem instanziierenden Typ vom Buildprozess generierten geladen) kompiliert werden, wenn die verweisende Aktivität geladen wird dynamisch (z. B. mit ActivityXAMLServices), klicken Sie dann die referenzierte Assembly in einem anderen Projekt platziert werden soll, oder der XAML-Designer generierter Code muss manuell bearbeitet werden, um dies zu ermöglichen.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Verwenden einer benutzerdefinierten Aktivität in einem Workflowprojekt  
  
1.  Fügen Sie einen Verweis vom Hostprojekt zum Aktivitätsbibliotheksprojekt hinzu, in dem die benutzerdefinierte Aktivität enthalten ist.  
  
2.  Erstellen Sie die Projektmappe.  
  
3.  Um die benutzerdefinierte Aktivität im Designer zu verwenden, identifizieren Sie die benutzerdefinierte Aktivität in der Toolbox, und ziehen Sie die Aktivität auf die Designeroberfläche.  
  
4.  Um die benutzerdefinierte Aktivität im Code zu verwenden, fügen Sie eine Using-Anweisung hinzu, die auf das benutzerdefinierte Aktivitätsprojekt verweist, und übergeben Sie eine neue Instanz der Aktivität an <xref:System.Activities.WorkflowInvoker.Invoke%2A>.
