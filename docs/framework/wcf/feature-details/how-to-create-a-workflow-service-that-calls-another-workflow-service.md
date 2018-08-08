---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Aufrufen eines anderen Workflowdiensts'
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: fda5a7286c3d20c7cdc2093e58bfe3fbdcf1d1c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497190"
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a>Vorgehensweise: Erstellen eines Workflowdiensts zum Aufrufen eines anderen Workflowdiensts
Unter bestimmten Umständen ist es erforderlich, dass Informationen von Workflowdiensten von anderen Workflowdiensten abgerufen werden.  In diesem Thema wird veranschaulicht, wie Sie einen Workflowdienst in einem anderen Workflowdienst aufrufen können. In diesem Thema werden zwei Workflowdienste erstellt: ein Workflowdienst mit einer Methode zur Umkehrung der Eingabezeichenfolge und ein Workflowdienst zur Konvertierung der umgekehrten Eingabezeichenfolge in Großbuchstaben.  
  
### <a name="to-create-the-reverser-workflow-service"></a>So erstellen Sie den Reverser-Workflowdienst  
  
1.  Führen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator aus.  
  
2.  Wählen Sie **Datei**, **neues Projekt**. Klicken Sie unter der **Workflow** Knoten in der **installierte Vorlagen** klicken Sie im Bereich **WCF-Workflowdienstanwendung**. Nennen Sie die Projektmappe `NestedServices` , und klicken Sie dann auf **OK**.  
  
3.  Klicken Sie unter **Server**, stellen Sie sicher, dass **lokalen IIS-Webserver verwenden** ausgewählt ist. Klicken Sie auf **erstellt ein virtuelles Verzeichnis**. Klicken Sie auf **OK** in der Meldung, dass das virtuelle Verzeichnis wurde erfolgreich erstellt wurde.  
  
4.  Benennen Sie im Projektmappen-Explorer Service1.xamlx zu `StringReverserService.xamlx`.  
  
5.  Auf der **Projekteigenschaften** Seite für das neue Projekt, klicken Sie auf die **Web** Registerkarte. Legen Sie die **Startaktion** auf **bestimmte Seite**, und wählen Sie StringReverserService.xamlx als Startseite.  
  
6.  Öffnen Sie StringReverserService.xamlx im Designer, löschen Sie die vorhandenen Aktivitäten `ReceiveRequest` und `SendReply`, und ziehen Sie eine `ReceiveAndSendReply`-Aktivität in die vorhandene Sequenzaktivität.  
  
    1.  Legen Sie die **OperationName** auf reversestring fest.  
  
    2.  Legen Sie die **ServiceContractName** auf ireversestring fest.  
  
    3.  Wählen Sie die **CanCreateInstance** Kontrollkästchen.  
  
7.  Wählen Sie die **SequentialService** Aktivität aus, und klicken Sie dann auf die **Variablen** Registerkarte am unteren Rand des Designers. Erstellen Sie zwei neue Variablen vom Typ String mit den Namen StringToReverse und ReversedStringToReturn.  
  
8.  Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **Receive** Aktivität. Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen InputString vom Typ String, der StringToReverse zugewiesen.  
  
9. Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **SendReplyToReceive** Aktivität. Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen ReversedString vom Typ String, ReversedStringToReturn zugewiesen.  
  
10. Erstellen Sie im Projekt eine neue Klasse mit dem Namen StringLibrary, um die Logik für den Dienst zu implementieren.  Ersetzen Sie die Klassendefinition durch den folgenden Code:  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. Um die ReverseString-Methode für die Eingabe aufzurufen, ziehen Sie ein **InvokeMethod** Aktivität aus der Toolbox auf den Abstand zwischen den **Receive** und **SendReply** Aktivitäten. Legen Sie die Eigenschaften der Aktivität wie folgt fest:  
  
    1.  **Methodenname**: ReverseString  
  
    2.  **Ergebnis**: ReversedStringToReturn  
  
    3.  **Parameter**: Erstellen Sie einen neuen Parameter mit einem **Richtung** von In, eine **Typ** -Zeichenfolge, und ein **Wert** stringtoreverse.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. Testen Sie den Dienst durch Drücken von F5. Doppelklicken Sie im angezeigten WCF-Testclient auf die ReverseString()-Methode. Geben Sie im Bereich Anforderung `Sample` für den Wert der InputString-Parameter. Klicken Sie auf **Aufrufen**. Die Rückgabe des Diensts sollte "elpmaS" lauten.  
  
### <a name="to-create-the-uppercaser-workflow-service"></a>So erstellen Sie den UpperCaser-Workflowdienst  
  
1.  Mit der rechten Maustaste des NestedServices-Projekts, und wählen Sie **hinzufügen**, **neues Element**. In der **Workflow** Knoten **WCF-Workflowdienst**, und nennen Sie den neuen Dienst `UpperCaserService`. Klicken Sie auf **Hinzufügen**. Dadurch sollte dem Projekt der neue Workflowdienst UpperCaserService.xamlx hinzugefügt werden.  
  
2.  Öffnen Sie UpperCaserService.xamlx im Designer, und löschen Sie die vorhandene **ReceiveRequest** und `SendReply` Aktivitäten, und ziehen Sie eine `ReceiveAndSendReply` Aktivität in die vorhandene Sequenzaktivität.  
  
    1.  Legen Sie die **OperationName** auf UppercaseString fest.  
  
    2.  Legen Sie die **ServiceContractName** auf iuppercasestring fest.  
  
    3.  Wählen Sie die **CanCreateInstance** Kontrollkästchen.  
  
3.  Wählen Sie die Aktivität sequentialservice aus, und klicken Sie dann auf die **Variablen** Registerkarte am unteren Rand des Designers. Erstellen Sie drei neue Variablen vom Typ String mit den Namen StringToUpper, StringToReverse und StringToReturn.  
  
4.  Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **Receive** Aktivität. Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen InputString vom Typ String, der StringToUpper zugewiesen.  
  
5.  Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **SendReplyToReceive** Aktivität. Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen ModifiedString vom Typ String, StringToReturn zugewiesen.  
  
6.  Erstellen Sie mit dem folgenden Code eine neue Methode in der StringLibrary-Klasse, um die Logik für den Dienst zu implementieren.  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  Um die UpperCaseString-Methode für die Eingabe aufzurufen, ziehen Sie ein **InvokeMethod** Aktivität aus der Toolbox auf den Abstand zwischen den **Receive** und **SendReply** Aktivitäten. Legen Sie die Eigenschaften der Aktivität wie folgt fest:  
  
    1.  **Methodenname**: UpperCaseString  
  
    2.  **Ergebnis**: StringToReverse  
  
    3.  **Parameter**: Erstellen Sie einen neuen Parameter mit einem **Richtung** von In, eine **Typ** -Zeichenfolge, und ein **Wert** stringtoupper.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  Nun wird der erste Dienst für die geänderte Zeichenfolge aufgerufen. Mit der rechten Maustaste des Projekts, und wählen Sie **Hinzufügen eines Dienstverweises**. Hinzufügen eines Dienstverweises an den Dienst unter http://localhost/NestedServices/StringReverserService.xamlx und erstellen Sie das Projekt, um eine benutzerdefinierte Aktivität für den Zugriff auf den ersten Webdienst zu erstellen.  
  
9. Ziehen Sie eine Instanz der neuen Aktivität den Workflow zwischen den **InvokeMethod** Aktivität und die **SendReplyToReceive** Aktivitäten. Weisen Sie der InputString-Eigenschaft der neuen Aktivität die StringToReverse-Variable zu, und weisen Sie der StringToReturn-Eigenschaft die StringToReturn-Variable zu.  
  
10. Öffnen Sie die Eigenschaftenseite des NestedServices-Projekts, und Ändern der **bestimmte Seite** in der **Web** Registerkarte in UpperCaserService.xamlx.  
  
11. Testen Sie den Dienst durch Drücken von F5. Doppelklicken Sie im angezeigten WCF-Testclient auf die ReverseString()-Methode. Geben Sie im Bereich Anforderung `Sample` für den Wert der InputString-Parameter. Klicken Sie auf **Aufrufen**. Die Rückgabe des Diensts sollte "ELPMAS" lauten.  
  
### <a name="to-create-a-client-to-call-the-services"></a>So erstellen Sie einen Client, der die Dienste aufruft  
  
1.  Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen Client hinzu.  
  
2.  Maustaste auf das Clientprojekt, und wählen Sie **Hinzufügen eines Dienstverweises**. Klicken Sie im Fenster, das angezeigt wird, auf **Discover**. Wählen Sie StringReverserService.xamlx aus, und geben Sie ReverseService als Namespace an.  Klicken Sie auf **OK**.  
  
3.  Ersetzen Sie die Main-Methode in der Datei Program.cs durch den folgenden Code:  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
