---
title: "Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 1e6ddb6fcee23bbabd66d9295c5ff1534140175a
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)
Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.  
  
 Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.  
  
### <a name="sharing-an-assembly"></a>Freigeben einer Assembly  
  
1.  Erstellen Ihrer Assembly. Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Weisen Sie Ihrer Assembly einen starken Namen zu. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Weisen Sie Ihrer Assembly Versionsinformationen zu. Weitere Informationen dazu finden Sie unter [Assemblyversionen](https://msdn.microsoft.com/library/51ket42z).  
  
4.  Fügen Sie Ihre Assembly in den globalen Assemblycache ein. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly in den globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind. Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)   
 [Programmieren mit Assemblys](../../../../framework/app-domains/programming-with-assemblies.md)
