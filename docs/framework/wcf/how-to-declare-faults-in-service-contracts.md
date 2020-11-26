---
title: 'Vorgehensweise: Deklarieren von Fehlern in Dienstverträgen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 06262d5f698f8898e162e92dad272a7188897af0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240055"
---
# <a name="how-to-declare-faults-in-service-contracts"></a>Vorgehensweise: Deklarieren von Fehlern in Dienstverträgen

In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst. In Windows Communication Foundation (WCF)-Anwendungen geben Dienstverträge jedoch an, welche Fehlerinformationen an Clients zurückgegeben werden, indem Sie SOAP-Fehler im Dienstvertrag deklarieren. Eine Übersicht über die Beziehung zwischen Ausnahmen und Fehlern finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md).

## <a name="create-a-service-contract-that-specifies-a-soap-fault"></a>Erstellen eines Dienstvertrags zum Angeben eines SOAP-Fehlers

1. Erstellen Sie einen Dienstvertrag, der mindestens einen Vorgang enthält. Ein Beispiel finden Sie unter Gewusst [wie: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md).

2. Wählen Sie einen Vorgang aus, der sich zum Angeben einer Fehlerbedingung eignet, aufgrund derer die Clients eine entsprechende Benachrichtigung erhalten. Informationen zur Entscheidung, welche Fehlerbedingungen die Rückgabe von SOAP-Fehlern an Clients begründen, finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md).

3. Wenden Sie ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> auf den ausgewählten Vorgang an, und geben Sie einen serialisierbaren Fehlertyp an den Konstruktor weiter. Ausführliche Informationen zum Erstellen und Verwenden von serialisierbaren Typen finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](./feature-details/specifying-data-transfer-in-service-contracts.md). Im folgenden Beispiel wird gezeigt, wie angegeben werden kann, dass der `SampleMethod`-Vorgang zu einem `GreetingFault` führt.

     [!code-csharp[FaultContractAttribute#4](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]

4. Wiederholen Sie die Schritte2 und 3 für alle Vorgänge des Vertrags, durch die Fehlerbedingungen an Clients weitergegeben werden.

## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a>Implementieren eines Vorgangs für das Zurückgeben eines angegebenen SOAP-Fehlers

 Nachdem für einen Vorgang angegeben wurde, dass ein bestimmter SOAP-Fehler zurückgegeben werden kann, um eine Fehlerbedingung an eine aufrufende Anwendung weiterzugeben (wie beispielsweise in der vorangehenden Prozedur beschrieben), besteht der nächste Schritt in der Implementierung dieser Angabe.

### <a name="throw-the-specified-soap-fault-in-the-operation"></a>Auslösen des angegebenen SOAP-Fehlers im Vorgang

1. Tritt in einem Vorgang eine durch <xref:System.ServiceModel.FaultContractAttribute> angegebene Fehlerbedingung auf, lösen Sie eine neue <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> aus. Der angegebene SOAP-Fehler fungiert hierbei als Typparameter. Im folgenden Beispiel wird gezeigt, wie der `GreetingFault` in der im vorherigen Abschnitt gezeigten `SampleMethod` sowie im folgenden Codeabschnitt ausgelöst werden kann.

     [!code-csharp[FaultContractAttribute#5](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt die Implementierung eines Einzelvorgangs, durch den ein `GreetingFault` für den `SampleMethod`-Vorgang angegeben wird.

[!code-csharp[FaultContractAttribute#1](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
[!code-vb[FaultContractAttribute#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
