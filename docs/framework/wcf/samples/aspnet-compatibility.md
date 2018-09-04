---
title: ASP.NET-Kompatibilität
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: eeb09914fc90848c987127c789379549917063f6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659512"
---
# <a name="aspnet-compatibility"></a>ASP.NET-Kompatibilität
Dieses Beispiel veranschaulicht, wie ASP.NET Kompatibilitätsmodus in Windows Communication Foundation (WCF) zu aktivieren. Dienste, die unter ASP.NET-Kompatibilität Modus nehmen uneingeschränkt an der ASP.NET-Pipeline für die Anwendung und können ASP.NET-Funktionen wie z. B. Datei-/URL-Autorisierung, Sitzungsstatus, verwenden und die <xref:System.Web.HttpContext> Klasse. Die <xref:System.Web.HttpContext> Klasse ermöglicht den Zugriff auf Cookies, Sitzungen und andere ASP.NET-Funktionen. Dieser Modus erfordert, dass die Bindungen den HTTP-Transport verwenden und der Dienst selbst in IIS gehostet ist.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (eine ausführbare Datei), und der Dienst wird in Internetinformationsdiensten (IIS) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
Damit das Beispiel ausgeführt werden kann, muss ein [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]-Anwendungspool verfügbar sein. Führen Sie die folgenden Schritte aus, um einen neuen Anwendungspool zu erstellen oder den Standardanwendungspool zu ändern.  

1.  Open **Systemsteuerung**.  Öffnen der **Verwaltung** Applet unter der **System und Sicherheit** Überschrift. Öffnen der **(Internet Information Services, IIS) Manager** Applet.  

2.  Erweitern Sie die Strukturansicht, in der **Verbindungen** Bereich. Wählen Sie die **Anwendungspools** Knoten.  

3.  Festlegen der Standardanwendungspool mit [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (Dies verursacht möglicherweise Inkompatibilitätsprobleme mit vorhandenen Websites), mit der rechten Maustaste die **DefaultAppPool** Listenelement aus, und wählen Sie **Grundeinstellungen...** . Legen Sie die **.Net Framework-Version** Pulldownliste **.Net Framework v4.0.30128** (oder höher).  

4.  Um einen neuen Anwendungspool zu erstellen, die verwendet [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (um die Kompatibilität mit anderen Anwendungen beizubehalten), mit der rechten Maustaste die **Anwendungspools** Knoten, und wählen **Anwendungspool hinzufügen...** . Benennen Sie den neuen Anwendungspool, und legen Sie die **.Net Framework-Version** Pulldownliste **.Net Framework-v4.0.30128** (oder höher). Nach dem Ausführen des Setups unten aufgeführten Schritte, mit der rechten Maustaste die **ServiceModelSamples** Anwendung, und wählen **-Anwendung verwalten**, **Erweiterte Einstellungen...** . Legen Sie die **Anwendungspool** an den neuen Anwendungspool.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen rechnerdienst implementiert. Der `ICalculator`-Vertrag wurde als `ICalculatorSession`-Vertrag geändert, damit eine Reihe von Vorgängen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.  
  
```csharp  
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
  
 Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst mithilfe der Funktion den Status für jeden Client bei. Der Client kann das aktuelle Ergebnis abrufen, indem er `Result` aufruft, und es auf null löschen, indem er `Clear` aufruft.  
  
 Der Dienst verwendet die ASP.NET-Sitzung, um das Ergebnis für jede Clientsitzung zu speichern. Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jeden Client über mehrere Aufrufe des Diensts hinweg beizubehalten.  
  
> [!NOTE]
> Der ASP.NET-Sitzungszustand und WCF-Sitzungen sind unterschiedliche Dinge. Finden Sie unter [Sitzung](../../../../docs/framework/wcf/samples/session.md) ausführliche Informationen zum WCF-Sitzungen.
  
 Der Dienst verfügt über eine enge Abhängigkeit für den ASP.NET-Sitzungszustand und erfordert ASP.NET-Kompatibilitätsmodus ordnungsgemäß funktioniert. Diese Anforderungen werden deklarativ durch die Übernahme des `AspNetCompatibilityRequirements`-Attributs ausgedrückt.  
  
```csharp  
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
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples-Anwendung in [!INCLUDE[iisver](../../../../includes/iisver-md.md)] einzurichten. Das Verzeichnis ServiceModelSamples sollte jetzt als [!INCLUDE[iisver](../../../../includes/iisver-md.md)]-Anwendung angezeigt werden.  
  
4.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting- und-persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
