---
title: Der Friend-Assemblyverweis <reference> ist ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160710"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a>BC31535: friend-Assemblyverweis \<reference> ist ungültig.

Der friend-Assemblyverweis \<reference> ist ungültig. Signierte Assemblys mit starkem Namen müssen in ihren InternalsVisibleTo-Deklarationen einen öffentlichen Schlüssel angeben.

 Der AssemblyName, der an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor übergeben wird, identifiziert eine Assembly mit starkem Namen, aber kein- `PublicKey` Attribut.

 **Fehler-ID:** BC31535

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Bestimmen Sie den öffentlichen Schlüssel für die Friend-Assembly mit starkem Namen. Fügen Sie den öffentlichen Schlüssel als Teil des Assemblynamens ein, der mit dem-Attribut an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attributkonstruktor übergeben wird `PublicKey` .

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.AssemblyName>
- [Friend-Assemblys](../../../standard/assembly/friend.md)
