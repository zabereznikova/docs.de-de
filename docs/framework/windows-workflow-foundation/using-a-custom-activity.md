---
title: Verwenden einer benutzerdefinierten Aktivität
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 43addd4e69b7f7ac3ac5cd8e5bcd41397d8f0a67
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293324"
---
# <a name="using-a-custom-activity"></a>Verwenden einer benutzerdefinierten Aktivität

Aktivitäten, die von <xref:System.Activities.Activity> oder den Unterklassen abgeleitet werden, können zu größeren Workflows zusammengesetzt oder direkt im Code erstellt werden. In diesem Thema wird beschrieben, wie Sie benutzerdefinierte Aktivitäten in Workflows verwenden, die entweder im Code oder im Designer erstellt wurden.  
  
> [!NOTE]
> Benutzerdefinierte Aktivitäten können im selben Projekt verwendet werden, in dem Sie definiert sind, solange die benutzerdefinierte Aktivität und die Aktivität, die Sie verwendet, kompiliert werden (d. h. durch einen vom Buildprozess generierten instanziierungstyp geladen), wenn die verweisende Aktivität dynamisch (z. b. mithilfe von ActivityXamlServices) geladen wird , oder der vom Designer generierte XAML-Code muss Hand bearbeitet werden, um dies zu ermöglichen.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Verwenden einer benutzerdefinierten Aktivität in einem Workflowprojekt  
  
1. Fügen Sie einen Verweis vom Hostprojekt zum Aktivitätsbibliotheksprojekt hinzu, in dem die benutzerdefinierte Aktivität enthalten ist.  
  
2. Erstellen Sie die Projektmappe.  
  
3. Um die benutzerdefinierte Aktivität im Designer zu verwenden, identifizieren Sie die benutzerdefinierte Aktivität in der Toolbox, und ziehen Sie die Aktivität auf die Designeroberfläche.  
  
4. Um die benutzerdefinierte Aktivität im Code zu verwenden, fügen Sie eine Using-Anweisung hinzu, die auf das benutzerdefinierte Aktivitätsprojekt verweist, und übergeben Sie eine neue Instanz der Aktivität an <xref:System.Activities.WorkflowInvoker.Invoke%2A>.
