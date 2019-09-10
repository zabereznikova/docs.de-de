---
title: 'Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 27e756d8e44580d9205cc075367bce5a45536c69
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854678"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a>Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“
In diesem Thema wird beschrieben, wie eine parametrisierte gespeicherte Prozedur mithilfe der <xref:System.Data.EntityClient.EntityCommand>-Klasse ausgeführt wird.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1. Fügen Sie dem Projekt das [Modell "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) " hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.  
  
2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Importieren Sie die gespeicherte `GetStudentGrades`-Prozedur, und geben Sie `CourseGrade`-Entitäten als Rückgabetyp an. Informationen zum Importieren einer gespeicherten Prozedur finden [Sie unter Gewusst wie: Importieren Sie eine gespeicherte](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100))Prozedur.  
  
## <a name="example"></a>Beispiel  
 Der folgenden Code führt die gespeicherte `GetStudentGrades`-Prozedur aus. Dabei ist `StudentId` ein erforderlicher Parameter. Die Ergebnisse werden dann von einer <xref:System.Data.EntityClient.EntityDataReader> gelesen.  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a>Siehe auch

- [EntityClient-Anbieter für Entity Framework](entityclient-provider-for-the-entity-framework.md)
