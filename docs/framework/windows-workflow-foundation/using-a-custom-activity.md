---
title: Verwenden einer benutzerdefinierten Aktivität
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 6ca67ef7a8c4330d0182e960fc3fdcce656976a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962224"
---
# <a name="using-a-custom-activity"></a>Verwenden einer benutzerdefinierten Aktivität
Aktivitäten, die von <xref:System.Activities.Activity> oder den Unterklassen abgeleitet werden, können zu größeren Workflows zusammengesetzt oder direkt im Code erstellt werden. In diesem Thema wird beschrieben, wie Sie benutzerdefinierte Aktivitäten in Workflows verwenden, die entweder im Code oder im Designer erstellt wurden.  
  
> [!NOTE]
> Benutzerdefinierte Aktivitäten können im selben Projekt verwendet werden, in dem Sie definiert sind, solange die benutzerdefinierte Aktivität und die Aktivität, die Sie verwendet, kompiliert werden (d. h. durch einen vom Buildprozess generierten instanziierungstyp geladen), wenn die referenzierende Aktivität geladen wird. dynamisch (z. b. mithilfe von ActivityXamlServices) sollte die Assembly, auf die verwiesen wird, in einem anderen Projekt abgelegt werden, oder der vom Designer generierte XAML muss Hand bearbeitet werden, um dies zu ermöglichen.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Verwenden einer benutzerdefinierten Aktivität in einem Workflowprojekt  
  
1. Fügen Sie einen Verweis vom Hostprojekt zum Aktivitätsbibliotheksprojekt hinzu, in dem die benutzerdefinierte Aktivität enthalten ist.  
  
2. Erstellen Sie die Projektmappe.  
  
3. Um die benutzerdefinierte Aktivität im Designer zu verwenden, identifizieren Sie die benutzerdefinierte Aktivität in der Toolbox, und ziehen Sie die Aktivität auf die Designeroberfläche.  
  
4. Um die benutzerdefinierte Aktivität im Code zu verwenden, fügen Sie eine Using-Anweisung hinzu, die auf das benutzerdefinierte Aktivitätsprojekt verweist, und übergeben Sie eine neue Instanz der Aktivität an <xref:System.Activities.WorkflowInvoker.Invoke%2A>.
