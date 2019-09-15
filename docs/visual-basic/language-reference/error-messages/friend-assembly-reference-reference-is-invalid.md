---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972391"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Friend-assemblyverweisverweis \<> ist ungültig.
Der Verweis \<> der Friend-Assembly ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.  
  
 Der AssemblyName, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> der an den Attributkonstruktor übergeben wird, identifiziert eine Assembly mit starkem Namen `PublicKey` , aber kein-Attribut.  
  
 **Fehler-ID:** BC31535  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Bestimmen Sie den öffentlichen Schlüssel für die Friend-Assembly mit starkem Namen. Fügen Sie den öffentlichen Schlüssel als Teil des Assemblynamens ein <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> , der mit dem `PublicKey` -Attribut an den Attributkonstruktor übergeben wird.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.AssemblyName>
- [Friend-Assemblys](../../../standard/assembly/friend.md)
