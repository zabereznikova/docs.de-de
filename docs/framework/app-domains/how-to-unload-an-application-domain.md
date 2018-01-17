---
title: "Gewusst wie: Entladen einer Anwendungsdomäne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5067651a9cb30602a7318380d469b6f6381d8756
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-unload-an-application-domain"></a>Gewusst wie: Entladen einer Anwendungsdomäne
Wenn Sie die Nutzung einer Anwendungsdomäne beenden möchten, entladen Sie sie mithilfe der <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>-Methode. Durch die **Unload**-Methode wird die angegebene Anwendungsdomäne ordnungsgemäß geschlossen. Während des Entladevorgangs können keine neuen Threads auf die Anwendungsdomäne zugreifen. Alle anwendungsdomänenspezifischen Strukturen werden freigegeben.  
  
 In die Anwendungsdomäne geladene Assemblys werden entfernt und sind nicht weiter verfügbar. Wenn eine in der Anwendungsdomäne enthaltene Assembly domänenneutral ist, verbleiben deren Daten im Speicher, bis der gesamte Prozess beendet wird. Das Beenden des gesamten Prozesses ist die einzige Möglichkeit, eine domänenneutrale Assembly zu entladen. Mitunter kann es vorkommen, dass das Entladen einer Anwendungsdomäne nicht erfolgreich ist und zu einer <xref:System.CannotUnloadAppDomainException> führt.  
  
 Im folgenden Codebeispiel wird eine neue Anwendungsdomäne mit dem Namen `MyDomain` erstellt, und es werden einige Informationen auf der Konsole ausgegeben. Anschließend wird die Anwendungsdomäne entladen. Beachten Sie, dass danach der Versuch gestartet wird, den angezeigten Namen der entladenen Anwendungsdomäne auf der Konsole auszugeben. Dadurch wird eine Ausnahme generiert, die von den „try/catch“-Anweisungen am Ende des Programms abgefangen wird.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Programming with Application Domains (Programmieren mit Anwendungsdomänen)](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [Gewusst wie: Erstellen einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)
