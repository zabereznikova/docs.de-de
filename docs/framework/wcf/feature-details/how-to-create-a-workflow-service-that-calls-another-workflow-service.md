---
title: "Vorgehensweise: Erstellen eines Workflowdiensts zum Aufrufen eines anderen Workflowdiensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: Erstellen eines Workflowdiensts zum Aufrufen eines anderen Workflowdiensts
Unter bestimmten Umständen ist es erforderlich, dass Informationen von Workflowdiensten von anderen Workflowdiensten abgerufen werden.In diesem Thema wird veranschaulicht, wie Sie einen Workflowdienst in einem anderen Workflowdienst aufrufen können.In diesem Thema werden zwei Workflowdienste erstellt: ein Workflowdienst mit einer Methode zur Umkehrung der Eingabezeichenfolge und ein Workflowdienst zur Konvertierung der umgekehrten Eingabezeichenfolge in Großbuchstaben.  
  
### So erstellen Sie den Reverser\-Workflowdienst  
  
1.  Führen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator aus.  
  
2.  Wählen Sie **Datei** und **Neues Projekt** aus.Wählen Sie unter dem Knoten **Workflow** im Bereich **Installierte Vorlagen** den Eintrag **WCF\-Workflowdienstanwendung** aus.Nennen Sie die Projektmappe `NestedServices`, und klicken Sie auf **OK**.  
  
3.  Vergewissern Sie sich, dass unter **Server** die Option **Lokalen IIS\-Webserver verwenden** ausgewählt ist.Klicken Sie auf **Virtuelles Verzeichnis erstellen**.Klicken Sie in der Meldung, dass das virtuelle Verzeichnis erfolgreich erstellt wurde, auf **OK**.  
  
4.  Benennen Sie im Projektmappen\-Explorer die Datei Service1.xamlx in `StringReverserService.xamlx` um.  
  
5.  Klicken Sie auf der Seite **Projekteigenschaften** des neuen Projekts auf die Registerkarte **Web**.Legen Sie die **Startaktion** auf **Bestimmte Seite** fest, und wählen Sie StringReverserService.xamlx als Startseite aus.  
  
6.  Öffnen Sie StringReverserService.xamlx im Designer, löschen Sie die vorhandenen Aktivitäten `ReceiveRequest` und `SendReply`, und ziehen Sie eine `ReceiveAndSendReply`\-Aktivität in die vorhandene Sequenzaktivität.  
  
    1.  Legen Sie **OperationName** auf ReverseString fest.  
  
    2.  Legen Sie **ServiceContractName** auf IReverseString fest.  
  
    3.  Aktivieren Sie das Kontrollkästchen **CanCreateInstance**.  
  
7.  Wählen Sie die Aktivität **SequentialService** aus, und klicken Sie unten im Designer auf die Registerkarte **Variablen**.Erstellen Sie zwei neue Variablen vom Typ String mit den Namen StringToReverse und ReversedStringToReturn.  
  
8.  Klicken Sie auf den Link **Definieren** in der **Receive**\-Aktivität.Klicken Sie auf **Parameter**, und erstellen Sie einen Parameter vom Typ String mit dem Namen InputString, der StringToReverse zugewiesen ist.  
  
9. Klicken Sie auf den Link **Definieren** in der **SendReplyToReceive**\-Aktivität.Klicken Sie auf **Parameter**, und erstellen Sie einen Parameter vom Typ String mit dem Namen ReversedString, der ReversedStringToReturn zugewiesen ist.  
  
10. Erstellen Sie im Projekt eine neue Klasse mit dem Namen StringLibrary, um die Logik für den Dienst zu implementieren.Ersetzen Sie die Klassendefinition durch den folgenden Code:  
  
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
  
11. Um die ReverseString\-Methode für die Eingabe aufzurufen, ziehen Sie eine **InvokeMethod**\-Aktivität aus der Toolbox in den Bereich zwischen der **Receive**\-Aktivität und der **SendReply**\-Aktivität.Legen Sie die Eigenschaften der Aktivität wie folgt fest:  
  
    1.  **MethodName**: ReverseString  
  
    2.  **Result**: ReversedStringToReturn  
  
    3.  **Parameter**: Erstellen Sie einen neuen Parameter mit der **Richtung** In, dem **Typ** String und dem **Wert** StringToReverse.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. Testen Sie den Dienst durch Drücken von F5.Doppelklicken Sie im angezeigten WCF\-Testclient auf die ReverseString\(\)\-Methode.Geben Sie im Bereich Anforderung `Sample` als Wert für den InputString\-Parameter ein.Klicken Sie auf **Aufrufen**.Die Rückgabe des Diensts sollte "elpmaS" lauten.  
  
### So erstellen Sie den UpperCaser\-Workflowdienst  
  
1.  Klicken Sie mit der rechten Maustaste auf das Projekt NestedServices, zeigen Sie auf **Hinzufügen**, und wählen Sie **Neues Element** aus.Wählen Sie unter dem Knoten **Workflow** den **WCF\-Workflowdienst** aus, und nennen Sie den neuen Dienst `UpperCaserService`.Klicken Sie auf **Hinzufügen**.Dadurch sollte dem Projekt der neue Workflowdienst UpperCaserService.xamlx hinzugefügt werden.  
  
2.  Öffnen Sie UpperCaserService.xamlx im Designer, löschen Sie die vorhandenen Aktivitäten **ReceiveRequest** und `SendReply`, und ziehen Sie eine `ReceiveAndSendReply`\-Aktivität in die vorhandene Sequenzaktivität.  
  
    1.  Legen Sie **OperationName** auf UpperCaseString fest.  
  
    2.  Legen Sie **ServiceContractName** auf IUpperCaseString fest.  
  
    3.  Aktivieren Sie das Kontrollkästchen **CanCreateInstance**.  
  
3.  Wählen Sie die Aktivität SequentialService aus, und klicken Sie unten im Designer auf die Registerkarte **Variablen**.Erstellen Sie drei neue Variablen vom Typ String mit den Namen StringToUpper, StringToReverse und StringToReturn.  
  
4.  Klicken Sie auf den Link **Definieren** in der **Receive**\-Aktivität.Klicken Sie auf **Parameter**, und erstellen Sie einen Parameter vom Typ String mit dem Namen InputString, der StringToUpper zugewiesen ist.  
  
5.  Klicken Sie auf den Link **Definieren** in der **SendReplyToReceive**\-Aktivität.Klicken Sie auf **Parameter**, und erstellen Sie einen Parameter vom Typ String mit dem Namen ModifiedString, der StringToReturn zugewiesen ist.  
  
6.  Erstellen Sie mit dem folgenden Code eine neue Methode in der StringLibrary\-Klasse, um die Logik für den Dienst zu implementieren.  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
  
    ```  
  
7.  Um die UpperCaseString\-Methode für die Eingabe aufzurufen, ziehen Sie eine **InvokeMethod**\-Aktivität aus der Toolbox in den Bereich zwischen der **Receive**\-Aktivität und der **SendReply**\-Aktivität.Legen Sie die Eigenschaften der Aktivität wie folgt fest:  
  
    1.  **MethodName**: UpperCaseString  
  
    2.  **Result**: StringToReverse  
  
    3.  **Parameter**: Erstellen Sie einen neuen Parameter mit der **Richtung** In, dem **Typ** String und dem **Wert** StringToUpper.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  Nun wird der erste Dienst für die geänderte Zeichenfolge aufgerufen.Klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Dienstverweis hinzufügen** aus.Fügen Sie dem Dienst unter http:\/\/localhost\/NestedServices\/StringReverserService.xamlx einen Dienstverweis hinzu, und erstellen Sie das Projekt, um eine benutzerdefinierte Aktivität für den Zugriff auf den ersten Webdienst zu erstellen.  
  
9. Ziehen Sie eine Instanz der neuen Aktivität zwischen der **InvokeMethod**\-Aktivität und der **SendReplyToReceive**\-Aktivität in den Workflow.Weisen Sie der InputString\-Eigenschaft der neuen Aktivität die StringToReverse\-Variable zu, und weisen Sie der StringToReturn\-Eigenschaft die StringToReturn\-Variable zu.  
  
10. Öffnen Sie die Eigenschaftenseite des NestedServices\-Projekts, und ändern Sie die **Bestimmte Seite** auf der Registerkarte **Web** in UpperCaserService.xamlx.  
  
11. Testen Sie den Dienst durch Drücken von F5.Doppelklicken Sie im angezeigten WCF\-Testclient auf die ReverseString\(\)\-Methode.Geben Sie im Bereich Anforderung `Sample` als Wert für den InputString\-Parameter ein.Klicken Sie auf **Aufrufen**.Die Rückgabe des Diensts sollte "ELPMAS" lauten.  
  
### So erstellen Sie einen Client, der die Dienste aufruft  
  
1.  Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen Client hinzu.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Clientprojekt, und wählen Sie **Dienstverweis hinzufügen** aus.Klicken Sie im angezeigten Fenster auf **Ermitteln**.Wählen Sie StringReverserService.xamlx aus, und geben Sie ReverseService als Namespace an.Klicken Sie auf **OK**.  
  
3.  Ersetzen Sie die Main\-Methode in der Datei Program.cs durch den folgenden Code:  
  
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