# JavaEE_enkelt

Ett försök till "enkla", kortfattade definitioner på svenska

Förslag på ändring? Gör en Issue. 
Förslag på tillägg? Gör en Pull request! 
All hjälp välkomnas!


----------------------------------------------------


Förkortningar

Ejb – Enterprise Java Beans, En javaklass som ger en del fördelar. Metoder blir transatkionella. EJB klasser är lätta att integrera med databaser. Man kan säkra EJB-metoder så bara inloggade användare kan nå dem. Metoder kan anropas från klientsidan (RMI).

RMI – Remote Method Invocation, klienten kan anropa metoder på servern.

JNDI – Java Naming and Directory Interface. Ett Java-API för en katalogservice som tillåter javaklienter att upptäcka och leta upp data och objekt via ett namn. Via denna blir resurserna, te.x. databas, tillgängliga globalt på servern, och ingen av dem som behöver nå databasen behöver ha inloggningsuppgifter.

CDI – Context and Dependency Injection. Möjliggör servern att injicera kod till klienten. Mer specifikt; servern kan tillhandahålla objekt och dess beroenden till klienten så den inte själv behöver skapa dem.

JPA – Java Persistence API. Gör det enkelt att lagra och läsa javaobjekt i en databas. Alternativet, som man slipper, är att översätta specifika objekt/interface till konkreta SQL-frågor.

SOAP – Simple Object Access Protocol. Används vid webbtjänster. Möjliggör tillsammans med WSDL för en klient att få tillgång till serverns metoder och anropa dem med hjälp av valfritt språk (till skillnad från RMI som kräver att klienten också är skriven i Java).

WSDL - Web Services Description Language. Ett XML-format för att beskriva webbtjänster och dess funktioner samt hur dessa anropas. 
Tillsammans med SOAP och UDDI är WSDL en av de tre grundstenarna för webbtjänster (Web Services). 

REST – arkitektonisk mönster. Saknar ultimat definition. Den som introducerade idén, Roy Fieldning, menar dock att det finns vissa principer. 
    • Servern hanterar applikationen och dess tillstånd . 
    • Servern sparar inte klientens tillstånd, utan det ansvarar den själv för. 
    • Servern måste meddela vad som kan lagras (chacheable), så klienten vet vad som ska sparas respektive slängas. 
    • Konsekvent gängsnitt mot servern. 
    • Systemen består av lager, och komponenter kan inte se annat än det som finns i dess eget lager.
 


Annotationer


Varje gång JNDI gör en lookup skapas ett nytt objekt i minnet på servern.
@Stateful – sparar attribut för objektet som är specifikt för EN klient. Används inte inte senare javaversioner.
@Stateless – Ett mer effetkivt sätt. Lagrar inte objeketet i minnet. Man vill lagrar i databas istället för bättre prestande/tar mindre resurser.

@Inject
Används för att injicera kod, se CDI.

@Local
Endast servern har tillgång.

@Remote
Klienten har tillgång.

Länkar
https://en.wikipedia.org/wiki/Loose_coupling
https://blog.ndepend.com/rest-vs-restful/
