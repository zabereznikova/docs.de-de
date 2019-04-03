---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0966cea26c5dde8f116081c7a6411b4275e50f40
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817044"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Friend-Assemblyverweis \<Verweis > ist ungültig.
Friend-Assemblyverweis \<Verweis > ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.  
  
 Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, aber er enthält keine `PublicKey` Attribut.  
  
 **Fehler-ID:** BC31535  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie den öffentlichen Schlüssel für den starken Namen der Friend-Assembly an. Die öffentlichen Schlüssel enthalten, wie Teil des Namens der Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.AssemblyName>
- [Friend-Assemblys](../../../standard/assembly/friend-assemblies.md)
