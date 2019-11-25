---
title: Ein Aufruf für eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als Rückgabewert.
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 53f9052555555a5b9dcb038dfee9cd54dc2b4251
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976199"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Ein Aufruf für eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als Rückgabewert.

Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- Ein Client hat eine Eigenschaft oder Methode einer Out-of-Process-Komponente aufgerufen und versucht, einen Verweis auf ein privates Objekt als eines der Argumente zu übergeben.  
  
- Eine Out-of-Process-Komponente hat eine Callback-Methode für ihren Client aufgerufen und versucht, einen Verweis auf ein privates Objekt zu übergeben  
  
- Eine Out-of-Process-Komponente hat versucht, einen Verweis auf ein privates Objekt als Argument eines Ereignisses zu übergeben, das von ihr ausgelöst wurde.  
  
- Ein Client hat versucht, einem `ByRef` -Argument eines Ereignisses, das er verarbeitet hat, einen privaten Objektverweis zuzuweisen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entfernen Sie den Verweis.  
  
## <a name="see-also"></a>Siehe auch

- [Private](../../../visual-basic/language-reference/modifiers/private.md)
