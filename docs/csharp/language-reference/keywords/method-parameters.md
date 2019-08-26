---
title: Methodenparameter – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 4011cbd3bc9306b64df87b1fcde48f1f41df8240
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602037"
---
# <a name="method-parameters-c-reference"></a>Methodenparameter (C#-Referenz)

Parameter, die ohne [in](./in-parameter-modifier.md), [ref](./ref.md) oder [out](./out-parameter-modifier.md) für eine Methode deklariert werden, werden nach Werten an die aufgerufene Methode übergeben. Dieser Wert kann in der Methode geändert werden, aber der geänderte Wert wird nicht gespeichert, wenn die aufrufende Prozedur wieder die Steuerung übernimmt. Wenn Sie ein Schlüsselwort für einen Methodenparameter verwenden, können Sie dieses Verhalten ändern.  
  
 In diesem Abschnitt wird das Schlüsselwort beschrieben, dass Sie verwenden können, wenn Sie Methodenparameter deklarieren.  
  
- Mit [params](./params.md) wird festgelegt, dass für diesen Parameter eine veränderliche Anzahl von Argumenten akzeptiert werden.
  
- Mit [in](./in-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird, jedoch nur von der aufgerufenen Methode gelesen wird.
  
- Mit [ref](./ref.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode gelesen oder geschrieben werden kann.
  
- Mit [out](./out-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode geschrieben wird.
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
