---
title: Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611929"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Friend-Assemblyverweis &lt;Verweis&gt; ist ungültig.
Friend-Assemblyverweis \<Verweis > ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.  
  
 Der Name der Assembly übergeben wird, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor identifiziert eine Assembly mit starkem Namen, aber er enthält keine `PublicKey` Attribut.  
  
 **Fehler-ID:** BC31535  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie den öffentlichen Schlüssel für den starken Namen der Friend-Assembly an. Die öffentlichen Schlüssel enthalten, wie Teil des Namens der Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor mithilfe der `PublicKey` Attribut.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Reflection.AssemblyName>
- [Friend-Assemblys](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


