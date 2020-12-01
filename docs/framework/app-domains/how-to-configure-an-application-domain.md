---
title: 'Vorgehensweise: Konfigurieren einer Anwendungsdomäne'
description: Konfigurieren einer Anwendungsdomäne in :NET Sie können die Common Language Runtime (CLR) mit Konfigurationsinformationen mithilfe der Klasse „AppDomainSetup“ für eine Anwendungsdomäne bereitstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: bbda1f75da6b994c54cd71c56f16615a3758859b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271511"
---
# <a name="how-to-configure-an-application-domain"></a>Vorgehensweise: Konfigurieren einer Anwendungsdomäne

Sie können die Common Language Runtime mit Konfigurationsinformationen mithilfe der <xref:System.AppDomainSetup>-Klasse für eine Anwendungsdomäne bereitstellen. Wenn Sie Ihre eigenen Anwendungsdomänen erstellen, ist die wichtigste Eigenschaft <xref:System.AppDomainSetup.ApplicationBase%2A>. Die anderen **AppDomainSetup**-Eigenschaften werden hauptsächlich von den Runtimehosts zur Konfiguration einer bestimmten Anwendungsdomäne verwendet.  
  
 Die Eigenschaft **ApplicationBase** definiert das Stammverzeichnis der Anwendung. Wenn die Runtime eine Typanforderung erfüllen muss, sucht sie nach der Assembly, die den Typ im Verzeichnis enthält, der von der **ApplicationBase**-Eigenschaft angegeben ist.  
  
> [!NOTE]
> Eine neue Anwendungsdomäne erbt nur die **ApplicationBase**-Eigenschaft des Erstellers.  
  
 Das folgende Beispiel erstellt eine Instanz der **AppDomainSetup**-Klasse, verwendet diese Klasse, um eine neue Anwendungsdomäne zu erstellen, schreibt die Informationen in die Konsole und entlädt die Anwendungsdomäne anschließend.  
  
## <a name="example"></a>Beispiel  

 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Programming with Application Domains (Programmieren mit Anwendungsdomänen)](application-domains.md#programming-with-application-domains)
- [Verwenden von Anwendungsdomänen](use.md)
