---
title: "ASP.NET-Kompatibilit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# ASP.NET-Kompatibilit&#228;t
In diesem Beispiel wird veranschaulicht, wie der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Kompatibilitätsmodus in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aktiviert wird.  Dienste, die im [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Kompatibilitätsmodus ausgeführt werden, nehmen vollständig an der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendungspipeline teil und können [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Funktionen, wie Datei\-\/URL\-Autorisierung, Sitzungsstatus und die <xref:System.Web.HttpContext>\-Klasse, nutzen.  Die <xref:System.Web.HttpContext>\-Klasse lässt Zugriff auf Cookies, Sitzungen und andere [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Funktionen zu.  Dieser Modus erfordert, dass die Bindungen den HTTP\-Transport verwenden und der Dienst selbst in IIS gehostet ist.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung \(eine ausführbare Datei\), und der Dienst wird in Internetinformationsdiensten \(IIS\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!NOTE]
>  Damit das Beispiel ausgeführt werden kann, muss ein [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]\-Anwendungspool verfügbar sein.  Führen Sie die folgenden Schritte aus, um einen neuen Anwendungspool zu erstellen oder den Standardanwendungspool zu ändern.  
>   
>  1.  Öffnen Sie die **Systemsteuerung**.  Öffnen Sie **Verwaltung** unter der Überschrift **System und Sicherheit**.  Öffnen Sie das Applet **Internetinformationsdienste\-Manager**.  
> 2.  Erweitern Sie die Strukturansicht im Bereich **Verbindungen**.  Wählen Sie den Knoten **Anwendungspools** aus.  
> 3.  Wenn Sie den Standardanwendungspool auf [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] festlegen möchten \(dies verursacht möglicherweise Inkompatibilitätsprobleme mit vorhandenen Websites\), klicken Sie mit der rechten Maustaste auf das Listenelement **DefaultAppPool**, und wählen Sie **Grundeinstellungen** aus.  Legen Sie in der Pulldownliste **.NET Framework\-Version** die Version **.NET Framework v4.0.30128** \(oder höher\) fest.  
> 4.  Um einen neuen Anwendungspool zu erstellen, der [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] verwendet \(um die Kompatibilität mit anderen Anwendungen beizubehalten\), klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungspools**, und wählen Sie **Anwendungspool hinzufügen** aus.  Benennen Sie den neuen Anwendungspool, und legen Sie in der Pulldownliste **.NET Framework\-Version** die Version auf **.NET Framework v4.0.30128** \(oder höher\) fest.  Klicken Sie nach Ausführung der Setupschritte unten mit der rechten Maustaste auf die Anwendung **ServiceModelSamples**, und wählen Sie **Anwendung verwalten**, **Erweiterte Einstellungen** aus.  Legen Sie **Anwendungspool** auf den neuen Anwendungspool fest.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), in dem ein Rechnerdienst implementiert wird.  Der `ICalculator`\-Vertrag wurde als `ICalculatorSession`\-Vertrag geändert, damit eine Reihe von Vorgängen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
  
```  
  
 Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst mithilfe der Funktion den Status für jeden Client bei.  Der Client kann das aktuelle Ergebnis abrufen, indem er `Result` aufruft, und es auf null löschen, indem er `Clear` aufruft.  
  
 Der Dienst verwendet die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Sitzung, um die Ergebnisse für jede Clientsitzung zu speichern.  Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jeden Client über mehrere Aufrufe des Diensts hinweg beizubehalten.  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Sitzungsstatus und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzungen sind unterschiedliche Dinge.  Weitere Informationen zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzungen finden Sie unter [Sitzung](../../../../docs/framework/wcf/samples/session.md).  
  
 Der Dienst verfügt über eine enge Abhängigkeit vom [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Sitzungsstatus und erfordert den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Kompatibilitätsmodus, um korrekt zu arbeiten.  Diese Anforderungen werden deklarativ durch die Übernahme des `AspNetCompatibilityRequirements`\-Attributs ausgedrückt.  
  
```  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.  Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
  
```  
  
### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Vergewissern Sie sich, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
3.  Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples\-Anwendung in [!INCLUDE[iisver](../../../../includes/iisver-md.md)] einzurichten.  Das Verzeichnis ServiceModelSamples sollte jetzt als [!INCLUDE[iisver](../../../../includes/iisver-md.md)]\-Anwendung angezeigt werden.  
  
4.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Siehe auch  
 [AppFabric\-Hosting\- und \-Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)