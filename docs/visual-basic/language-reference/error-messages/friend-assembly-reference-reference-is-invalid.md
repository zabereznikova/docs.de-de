---
title: Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: c47fae9c60dc04ee02b1ff015d3dde87b8920c02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
Friend-Assemblyverweis \<Verweis > ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.  
  
 Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, jedoch nicht mitgespeichert ein `PublicKey` Attribut.  
  
 **Fehler-ID:** BC31535  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie den öffentlichen Schlüssel für die Assembly mit starkem Namen "Friend". Den öffentlichen Schlüssel enthalten, als Teil der Assemblyname übergeben der <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.AssemblyName>  
 [Friend-Assemblys](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

