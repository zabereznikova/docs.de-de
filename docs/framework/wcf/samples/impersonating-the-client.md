---
title: "Durchf&#252;hren eines Identit&#228;tswechsels f&#252;r den Client | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Durchführen eines Identitätswechsels für den Client (Beispiel) [Windows Communication Foundation]"
  - "Identitätswechsel, Windows Communication Foundation-Beispiel"
  - "Dienstverhalten, Beispiel für Identitätswechsel"
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Durchf&#252;hren eines Identit&#228;tswechsels f&#252;r den Client
Das Beispiel für einen Identitätswechsel veranschaulicht, wie die Identität der Aufruferanwendung vom Dienst angenommen wird, sodass der Dienst im Namen des Aufrufers auf Systemressourcen zugreifen kann.  
  
 Dieses Beispiel basiert auf dem Beispiel [Selbst gehostete Dienste](../../../../docs/framework/wcf/samples/self-host.md).Der Dienst und die Clientkonfigurationsdateien sind mit denen des Beispiels [Selbst gehostete Dienste](../../../../docs/framework/wcf/samples/self-host.md) identisch.  
  
> [!NOTE]
>  Die Setupprozedur und Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im folgenden Codebeispiel wird gezeigt, dass der Servicecode so geändert wurde, dass die `Add`\-Methode für den Dienst die Identität des Aufrufers mithilfe von <xref:System.ServiceModel.OperationBehaviorAttribute> annimmt.  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
  
```  
  
 Demzufolge wird der Sicherheitskontext des ausgeführten Threads so geändert, dass die Identität des Aufrufers angenommen wird, bevor die `Add`\-Methode eingegeben und auf das Beenden der Methode zurückgesetzt wird.  
  
 Die im folgenden Codebeispiel veranschaulichte `DisplayIdentityInformation`\-Methode ist eine Hilfsfunktion, mit der die Identität des Aufrufers dargestellt wird.  
  
```  
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",   
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
  
```  
  
 Im folgenden Codebeispiel wird gezeigt, dass die `Subtract`\-Methode für den Dienst die Identität des Aufrufers mithilfe von imperativen Aufrufen annimmt.  
  
```  
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
Console.WriteLine("Before impersonating");  
DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs   
            // on the system resource are enforced in the caller's context.   
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
Console.WriteLine("After reverting");  
DisplayIdentityInformation();  
    return result;  
}  
```  
  
 Beachten Sie, dass in diesem Fall kein Identitätswechsel für den gesamten Aufruf, sondern nur für einen Teil des Aufrufs vorgenommen wurde.Im Allgemeinen empfiehlt es sich, einen Identitätswechsel für den kleinsten Bereich und nicht für den ganzen Vorgang durchzuführen.  
  
 Die anderen Methoden nehmen die Identität des Aufrufers nicht an.  
  
 Der Clientcode wurde geändert, um die Identitätswechselebene auf <xref:System.Security.Principal.TokenImpersonationLevel> festzulegen.Der Client gibt die vom Dienst zu verwendende Identitätswechselebene durch die <xref:System.Security.Principal.TokenImpersonationLevel>\-Enumeration an.Die Enumeration unterstützt die folgenden Werte: <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel> und <xref:System.Security.Principal.TokenImpersonationLevel>.Um beim Zugreifen auf die Systemressource auf dem lokalen Rechner, der mit Windows\-Zugriffssteuerungslisten geschützt ist, eine Zugriffsprüfung durchzuführen, muss die Identitätswechselebene auf <xref:System.Security.Principal.TokenImpersonationLevel> festgelegt sein, wie im folgenden Codebeispiel gezeigt.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst\- und Clientkonsolenfenster angezeigt.Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
> [!NOTE]
>  Der Dienst muss entweder auf einem Administratorkonto ausgeführt werden, oder das Konto, auf dem der Dienst ausgeführt wird, muss über Berechtigungen zum Registrieren des URI http:\/\/localhost:8000\/ServiceModelSamples mit der HTTP\-Ebene verfügen.Solche Rechte können durch Einrichten einer [Namespacereservierung](http://go.microsoft.com/fwlink/?LinkId=95012) \(möglicherweise nur in englischer Sprache\) mit dem [Tool Httpcfg.exe](http://go.microsoft.com/fwlink/?LinkId=95010) \(möglicherweise nur in englischer Sprache\) gewährt werden.  
  
> [!NOTE]
>  Auf Computern mit [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] wird der Identitätswechsel nur unterstützt, wenn die Host.exe\-Anwendung über eine Berechtigung zum Identitätswechsel verfügt.\(Standardmäßig verfügen nur Administratoren über diese Berechtigung.\) Wechseln Sie zum Hinzufügen dieser Berechtigung zu einem Konto, auf dem der Dienst ausgeführt wird, zu **Verwaltung**, öffnen Sie **Lokale Sicherheitsrichtlinie** und **Lokale Richtlinien**, und klicken Sie auf **Zuweisen von Benutzerrechten**. Wählen Sie dann die Option **Annehmen der Clientidentität nach Authentifizierung** aus, und doppelklicken Sie auf **Eigenschaften**, um einen Benutzer oder eine Gruppe hinzuzufügen.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder über Computer hinweg ausführen möchten, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4.  Wenn Sie veranschaulichen möchten, dass der Dienst die Identität des Aufrufers annimmt, führen Sie den Client auf einem anderen Konto als dem Konto aus, auf dem der Dienst ausgeführt wird.Geben Sie dazu an der Eingabeaufforderung Folgendes ein:  
  
    ```  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     Sie werden anschließend zur Eingabe eines Kennworts aufgefordert.Geben Sie das Kennwort für das Konto ein, das Sie vorher angegeben haben.  
  
5.  Wenn Sie den Client ausführen, beachten Sie die Identität vor und nach dem Ausführen mit unterschiedlichen Anmeldeinformationen.  
  
## Siehe auch