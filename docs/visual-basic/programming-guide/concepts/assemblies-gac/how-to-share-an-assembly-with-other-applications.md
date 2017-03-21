---
title: 'Gewusst wie: Freigeben einer Assembly mit einer anderen Anwendung (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8065a66c8f7c7b9ccb9125b060b0c03cde273482
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Gewusst wie: Freigeben einer Assembly mit einer anderen Anwendung (Visual Basic)
Assemblys können privat oder freigegeben sein: standardmäßig die meisten einfachen-Programme bestehen aus einer privaten Assembly, weil sie nicht von einer anderen Anwendung verwendet werden sollen.  
  
 Um eine Assembly mit einer anderen Anwendung freizugeben, muss Sie in platziert die [Global Assembly Cache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).  
  
### <a name="sharing-an-assembly"></a>Freigeben einer assembly  
  
1.  Erstellen Sie die Assembly. Weitere Informationen finden Sie unter [Assemblys erstellen](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).  
  
2.  Die Assembly einen starken Namen zuweisen. Weitere Informationen finden Sie unter [Gewusst wie: Signieren einer Assembly mit einem starken Namen](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).  
  
3.  Weisen Sie der Assembly Versionsinformationen. Weitere Informationen finden Sie unter [Assemblyversionen](https://msdn.microsoft.com/library/51ket42z).  
  
4.  Fügen Sie die Assembly im globalen Assemblycache hinzu. Weitere Informationen finden Sie unter [Gewusst wie: Installieren einer Assembly im globalen Assemblycache](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).  
  
5.  Zugriff auf die Typen in der Assembly aus dem anderen Programmen enthalten. Weitere Informationen finden Sie unter [Gewusst wie: Verweisen auf eine Assembly mit starkem Namen](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierkonzepte für die](../../../../visual-basic/programming-guide/concepts/index.md)
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Programmieren mit Assemblys](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)
