---
title: 'Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: d440000ef509199bf69f06c2f3b5d0819e48f724
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713576"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)
Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.  
  
 Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.  
  
### <a name="sharing-an-assembly"></a>Freigeben einer Assembly  
  
1.  Erstellen Ihrer Assembly. Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Weisen Sie Ihrer Assembly einen starken Namen zu. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Weisen Sie Ihrer Assembly Versionsinformationen zu. Weitere Informationen dazu finden Sie unter [Assemblyversionen](../../../../../docs/framework/app-domains/assembly-versioning.md).  
  
4.  Fügen Sie Ihre Assembly in den globalen Assemblycache ein. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind. Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)
- [Programmieren mit Assemblys](../../../../framework/app-domains/programming-with-assemblies.md)
