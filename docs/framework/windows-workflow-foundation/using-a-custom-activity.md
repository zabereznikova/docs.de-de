---
title: "Verwenden einer benutzerdefinierten Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Verwenden einer benutzerdefinierten Aktivit&#228;t
Aktivitäten, die von <xref:System.Activities.Activity> oder den Unterklassen abgeleitet werden, können zu größeren Workflows zusammengesetzt oder direkt im Code erstellt werden.In diesem Thema wird beschrieben, wie Sie benutzerdefinierte Aktivitäten in Workflows verwenden, die entweder im Code oder im Designer erstellt wurden.  
  
> [!NOTE]
>  Benutzerdefinierte Aktivitäten können im selben Projekt verwendet werden, in dem sie definiert wurden. Dazu muss jedoch sowohl die benutzerdefinierte Aktivität als auch die Aktivität, die diese verwendet, kompiliert werden \(d. h.von einem instanziierenden Typ geladen werden, der durch den Buildprozess generiert wird\). Wenn die Aktivität, auf die verwiesen wird, dynamisch geladen wird \(z. B. mithilfe vonActivityXAMLServices\), sollte die Assembly, auf die verwiesen wird, in einem anderen Projekt abgelegt werden. Andernfalls muss die vom Designer generierte XAML manuell bearbeitet werden, um dies zu ermöglichen.  
  
#### Verwenden einer benutzerdefinierten Aktivität in einem Workflowprojekt  
  
1.  Fügen Sie einen Verweis vom Hostprojekt zum Aktivitätsbibliotheksprojekt hinzu, in dem die benutzerdefinierte Aktivität enthalten ist.  
  
2.  Erstellen Sie die Projektmappe.  
  
3.  Um die benutzerdefinierte Aktivität im Designer zu verwenden, identifizieren Sie die benutzerdefinierte Aktivität in der Toolbox, und ziehen Sie die Aktivität auf die Designeroberfläche.  
  
4.  Um die benutzerdefinierte Aktivität im Code zu verwenden, fügen Sie eine Using\-Anweisung hinzu, die auf das benutzerdefinierte Aktivitätsprojekt verweist, und übergeben Sie eine neue Instanz der Aktivität an <xref:System.Activities.WorkflowInvoker.Invoke%2A>.