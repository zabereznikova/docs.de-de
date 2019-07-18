---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794523"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Erstellt eine Instanz der [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a>Parameter  
  
## <a name="parameter-values"></a>Parameterwerte  
 *operationDescription*  
  
 beschreibt den Vorgang, der in der zu generierenden Workflowaktivität ausgeführt werden soll, einschließlich des Vorgangsnamens, Rückgabetyps und Parameterinformationen. Der Wert dieses Parameters darf nicht sein **null**. Er sollte einen synchronen Vorgang beschreiben, der einen Nachrichtenvertrag und ein Argument mit einer Nachricht verwendet. Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.  
  
 *configurationName*  
  
 gibt den zu verwendenden Endpunkt-Konfigurationsnamen an. Der Wert dieses Parameters darf nicht sein, entweder **null** oder leer sein. Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.  
  
 *proxyNamespace*  
  
 gibt den Servicenamespace für den Vorgang an. Der Wert dieses Parameters darf nicht sein, entweder **null** oder leer sein. Wenn diese Bedingungen nicht erfüllt sind, ist das Laufzeitergebnis der Verwendung des Konstruktors und der anderen Methoden dieser Klasse nicht definiert.  
  
## <a name="see-also"></a>Siehe auch

- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
