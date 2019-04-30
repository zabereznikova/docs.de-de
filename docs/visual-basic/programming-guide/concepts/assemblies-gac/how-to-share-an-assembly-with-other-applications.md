---
title: 'Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 520fe69d30ca55251ae7a19dcd7a1ea0c11e7bd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022180"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (Visual Basic)
Assemblys können sowohl privat als auch freigegeben sein: Standardmäßig bestehen die meisten einfachen Programme aus einer privaten Assembly, da sie nicht für den Gebrauch durch andere Anwendungen vorgesehen sind.  
  
 Um eine Assembly für andere Anwendungen freizugeben, muss diese in den [globalen Assemblycache](../../../../framework/app-domains/gac.md) (Global Assembly Cache, GAC) platziert werden.  
  
### <a name="sharing-an-assembly"></a>Freigeben einer Assembly  
  
1. Erstellen Ihrer Assembly. Weitere Informationen finden Sie unter [Erstellen von Assemblys](../../../../framework/app-domains/create-assemblies.md).  
  
2. Weisen Sie Ihrer Assembly einen starken Namen zu. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3. Weisen Sie Ihrer Assembly Versionsinformationen zu. Weitere Informationen dazu finden Sie unter [Assemblyversionen](../../../../framework/app-domains/assembly-versioning.md).  
  
4. Fügen Sie Ihre Assembly in den globalen Assemblycache ein. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5. Greifen Sie auf die Typen anderer Anwendungen zu, die in der Assembly enthalten sind. Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Siehe auch

- [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
- [Assemblys in .NET](../../../../standard/assembly/index.md)
- [Programmieren mit Assemblys](../../../../framework/app-domains/programming-with-assemblies.md)
