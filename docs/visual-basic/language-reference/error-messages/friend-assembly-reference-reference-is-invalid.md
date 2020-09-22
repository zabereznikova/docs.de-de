---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874094"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Der Friend-Assemblyverweis \<reference> ist ungültig

Der friend-Assemblyverweis \<reference> ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.  
  
 Der AssemblyName, der an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor übergeben wird, identifiziert eine Assembly mit starkem Namen, aber kein- `PublicKey` Attribut.  
  
 **Fehler-ID:** BC31535  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Bestimmen Sie den öffentlichen Schlüssel für die Friend-Assembly mit starkem Namen. Fügen Sie den öffentlichen Schlüssel als Teil des Assemblynamens ein, der mit dem-Attribut an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor übergeben wird `PublicKey` .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Reflection.AssemblyName>
- [Friend-Assemblys](../../../standard/assembly/friend.md)
