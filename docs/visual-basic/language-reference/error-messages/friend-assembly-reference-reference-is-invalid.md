---
title: "Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
Friend-Assemblyverweis \<Verweis > ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.  
  
 Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, jedoch nicht mitgespeichert ein `PublicKey` Attribut.  
  
 **Fehler-ID:** BC31535  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie den öffentlichen Schlüssel für die Assembly mit starkem Namen "Friend". Den öffentlichen Schlüssel enthalten, als Teil der Assemblyname übergeben der <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.AssemblyName>  
 [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [Gewusst wie: Erstellen von signierten Friend-Assemblys](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
