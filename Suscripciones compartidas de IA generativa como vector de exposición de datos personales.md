# Suscripciones compartidas de IA generativa como vector de exposición de datos personales: una investigación extendida desde el cumplimiento normativo

Ruben Vasile Marcu Ungureanu (1 y 2), Fernando Andreu Royo (1) ((1) Asociación de Profesionales de la Privacidad en Aragón, (2) ARAINTEL Research Group)

Oct 1, 2026

## Resumen

Un mercado de intermediarios revende acceso compartido a suscripciones de asistentes de inteligencia artificial generativa por una fracción de su precio oficial. Este trabajo examina las consecuencias de ese modelo para la protección de datos personales mediante un estudio exploratorio sobre cuentas reales de ChatGPT adquiridas en plataformas de reventa, y un análisis jurídico conforme al RGPD, la LOPDGDD y la jurisprudencia del TJUE. Las cuentas analizadas, con hasta 14 dispositivos vinculados frente a los cuatro a seis usuarios anunciados, contenían informes médicos, documentación bancaria y administrativa, fotografías de espacios privados, información sobre menores y credenciales, accesibles para cualquier comprador posterior. Una de ellas almacenaba 615 archivos y 1.586 imágenes. Se proponen un modelo de amenaza con cinco vectores de exposición propios de los asistentes con almacenamiento persistente y un análisis de responsabilidades. Se concluye que el intermediario es responsable del tratamiento consistente en organizar y habilitar el acceso compartido al contenido almacenado en la cuenta, operación desprovista de base jurídica que vulnera la protección de datos por defecto del artículo 25.2 RGPD; que este trabajo sostiene la tesis de que esta arquitectura puede calificarse asimismo como una violación de la confidencialidad de carácter estructural y continuado en el sentido del artículo 4.12 RGPD; que el RGPD resultará aplicable al intermediario cuando se acredite que su oferta se dirige a interesados en la Unión (artículo 3.2 RGPD); que la arquitectura del modelo dificulta extraordinariamente el ejercicio efectivo de los derechos de los interesados (en particular el de supresión), pudiendo llegar a impedir de facto su satisfacción; y que el proveedor del servicio no agota necesariamente sus deberes de diligencia con la sola prohibición contractual de compartir cuentas. El trabajo formula recomendaciones para usuarios, organizaciones, proveedores y autoridades de control.

**Palabras clave:** protección de datos; RGPD; inteligencia artificial generativa; cuentas compartidas; violación de la seguridad; privacidad por defecto; responsable del tratamiento.

## Abstract

A market of intermediaries resells shared access to generative AI assistant subscriptions at a fraction of their official price. This paper examines the consequences of this model for personal data protection through an exploratory study of real ChatGPT accounts purchased on resale platforms, together with a legal analysis under the GDPR, Spanish data protection law and the case law of the Court of Justice of the European Union. The accounts analysed, with up to 14 linked devices against the four to six users advertised, contained medical reports, banking and administrative documents, photographs of private spaces, information about minors and credentials, all accessible to any later buyer. One account stored 615 files and 1,586 images. We propose a threat model with five exposure vectors specific to assistants with persistent storage and an analysis of responsibilities. We conclude that the intermediary is the controller of the processing operation consisting in organising and enabling shared access to the content stored in the account, which lacks a legal basis and infringes data protection by default under Article 25(2) GDPR; that this paper argues that this architecture may also be characterised as a structural, ongoing personal data breach of confidentiality under Article 4(12) GDPR; that the GDPR will apply to non-EU intermediaries where it is established that their offering is directed to data subjects in the Union (Article 3(2) GDPR); that the architecture of the model extraordinarily hinders the effective exercise of data subjects' rights (particularly erasure), potentially precluding their satisfaction de facto; and that the service provider does not necessarily discharge its diligence obligations merely by contractually prohibiting account sharing. We offer recommendations for users, organisations, providers and supervisory authorities.

**Keywords:** data protection; GDPR; generative artificial intelligence; account sharing; personal data breach; privacy by default; data controller.

## 1. Introducción

La reventa de acceso compartido a suscripciones de inteligencia artificial (IA) generativa convierte cada cuenta en un repositorio común de datos personales de desconocidos, que además persiste cuando cada comprador abandona el servicio. Este trabajo documenta ese fenómeno con evidencias obtenidas en cuentas reales de ChatGPT y lo analiza a la luz del Reglamento General de Protección de Datos (RGPD) y de la Ley Orgánica 3/2018 (LOPDGDD).

Los asistentes de IA generativa se han convertido en el lugar al que muchas personas acuden para entender documentos que no dominan: un informe médico, un extracto bancario, un contrato o una carta de la Administración. Al mismo tiempo, los proveedores han dotado a estos servicios de almacenamiento persistente: historiales de conversación, bibliotecas de archivos e imágenes y funciones de memoria capaces de tener en cuenta todas las conversaciones anteriores del usuario. Todo ello se diseña sobre una premisa explícita: la cuenta pertenece a una sola persona. Los términos de uso de OpenAI para el Espacio Económico Europeo establecen que el usuario no puede compartir sus credenciales ni poner su cuenta a disposición de terceros (OpenAI, 2026).

En paralelo ha surgido un mercado de intermediarios que venden acceso compartido a esas mismas suscripciones. En una de las plataformas analizadas, el acceso a ChatGPT se anunciaba por 4,16 € al mes, frente a los 20 dólares mensuales del precio oficial de ChatGPT Plus (OpenAI, s. f.-b). La diferencia solo se explica repartiendo una única suscripción entre varios compradores, que reciben las mismas credenciales y, con ellas, acceso a todo lo que los anteriores dejaron dentro.

La literatura sobre el uso compartido de cuentas se ha centrado en entornos de confianza, como hogares y parejas (Matthews et al., 2016; Obada-Obieh et al., 2020). El escenario que aquí se estudia es distinto en tres aspectos: los usuarios no se conocen entre sí, un intermediario comercial organiza el acceso con fines lucrativos y el servicio compartido acumula documentos e imágenes, no solo preferencias de uso. No nos consta ningún estudio previo que documente este fenómeno ni que lo analice desde el Derecho de protección de datos.

### 1.1. Preguntas de investigación

El trabajo se articula en torno a tres preguntas:

1. **PI1.** ¿Qué categorías de datos personales quedan expuestas a terceros en las cuentas de IA generativa revendidas como acceso compartido, y a través de qué vectores?
2. **PI2.** ¿Cómo se califican jurídicamente, conforme al RGPD y la LOPDGDD, los tratamientos que genera este modelo, y qué sujetos responden de ellos?
3. **PI3.** ¿Qué derechos pueden ejercer de forma efectiva las personas afectadas y qué medidas corresponden a cada actor implicado?

### 1.2. Contribuciones

Este trabajo realiza cuatro contribuciones:

1. **Evidencia empírica.** Documenta, mediante un estudio exploratorio sobre cuentas reales, el funcionamiento del mercado de reventa de acceso a ChatGPT y la presencia en esas cuentas de categorías especiales de datos, datos de menores y credenciales de terceros servicios.
2. **Modelo de amenaza.** Identifica cinco vectores de exposición propios de los asistentes de IA con almacenamiento persistente, que distinguen este caso del uso compartido de servicios de vídeo o música.
3. **Análisis jurídico.** Delimita el ámbito de aplicación del RGPD frente a la exención doméstica, califica al intermediario como responsable del tratamiento consistente en organizar y habilitar el acceso compartido al contenido almacenado en la cuenta, y plantea que dicha arquitectura puede calificarse asimismo como una violación de la confidencialidad (artículo 4.12 RGPD) de carácter estructural y continuado, a la luz de la jurisprudencia del Tribunal de Justicia de la Unión Europea (TJUE).
4. **Recomendaciones.** Propone medidas diferenciadas para usuarios, organizaciones, proveedores de IA y autoridades de control.

### 1.3. Estructura del trabajo

La sección 2 revisa los antecedentes técnicos, regulatorios y académicos. La sección 3 describe la metodología, sus salvaguardas éticas y el modelo de amenaza. La sección 4 presenta los resultados empíricos y la sección 5 desarrolla el análisis jurídico. La sección 6 discute las implicaciones y formula recomendaciones, la sección 7 expone las limitaciones y la sección 8 recoge las conclusiones.

**Nota sobre la publicación previa.** Un avance periodístico de los hallazgos empíricos se publicó en el medio ARAINTEL el 22 de septiembre de 2026 (Marcu, 2026). El presente trabajo es una investigación extendida de aquellos hallazgos desde la perspectiva del cumplimiento normativo: incorpora una metodología explícita, un modelo de amenaza y un análisis jurídico conforme al RGPD, la LOPDGDD y la jurisprudencia del TJUE, ninguno de los cuales formaba parte de esa publicación.

## 2. Antecedentes y trabajo relacionado

El fenómeno estudiado se sitúa en la intersección de tres líneas: la investigación sobre uso compartido de cuentas, la evolución de los asistentes de IA hacia el almacenamiento persistente y la actividad de las autoridades de control sobre estos servicios.

### 2.1. Del uso compartido doméstico al mercado de reventa

La investigación en interacción persona-ordenador ha mostrado que compartir dispositivos y cuentas es una práctica cotidiana en los hogares, guiada por la comodidad y apoyada en relaciones de confianza (Matthews et al., 2016). Obada-Obieh et al. (2020) estudiaron la fase final de esa práctica y mostraron que dejar de compartir una cuenta resulta costoso: los usuarios no siempre saben qué accesos siguen activos ni qué información queda a la vista de quienes compartían la cuenta.

El mercado de reventa altera los supuestos de esos trabajos. Los usuarios ya no se conocen, la confianza entre ellos no existe y el acceso lo organiza un intermediario que obtiene un beneficio económico. La plataforma documentada en la sección 4 se presentaba con la afirmación de contar con "más de 10 millones de usuarios en más de 150 países" y ofrecía en el mismo catálogo suscripciones de IA, vídeo y música (figura 2). Esta afirmación comercial no ha sido verificada por los autores.

### 2.2. Almacenamiento persistente en los asistentes de IA generativa

Compartir una suscripción de vídeo expone, como mucho, un historial de visionado. Compartir un asistente de IA generativa expone mucho más, porque estos servicios conservan el contenido que el usuario introduce. ChatGPT mantiene el historial de conversaciones, una biblioteca de archivos e imágenes con cuota propia y funciones de memoria.

La memoria de ChatGPT opera en dos modalidades. Las memorias guardadas recogen detalles que el usuario pide expresamente recordar. La referencia al historial de conversaciones permite al sistema usar información relevante de conversaciones anteriores para personalizar respuestas futuras (OpenAI, s. f.-c), función anunciada en abril de 2025 (OpenAI Community, 2025). Según el propio proveedor, eliminar por completo una información exige borrar la memoria guardada, la conversación original y los archivos asociados, y la eliminación puede tardar en propagarse (OpenAI, s. f.-c).

En una cuenta individual, estas funciones sirven a su titular. En una cuenta compartida, operan sobre un perfil que mezcla a varias personas. El resultado es que los datos de un usuario pueden quedar no solo almacenados sino también incorporados a las respuestas que recibe otro.

### 2.3. Exposición de datos entre usuarios: precedentes

La exposición cruzada de datos entre usuarios de un asistente de IA tiene un precedente documentado. El 20 de marzo de 2023, un fallo en la biblioteca redis-py permitió que algunos usuarios de ChatGPT vieran títulos de conversaciones ajenas y expuso datos de pago del 1,2 % de los suscriptores de ChatGPT Plus activos durante una ventana de nueve horas (OpenAI, 2023). Aquel incidente fue accidental, acotado en el tiempo y corregido por el proveedor.

El riesgo de acceso a cuentas por terceros también está documentado. Group-IB (2023) identificó 101.134 dispositivos infectados por malware de robo de información que contenían credenciales de ChatGPT, y advirtió de que el historial de consultas que ChatGPT conserva por defecto podía exponer información sensible de empresas. El caso aquí estudiado combina ambos riesgos: el acceso de terceros a cuentas ajenas, pero organizado y vendido como servicio.

### 2.4. Actuaciones de las autoridades de control

El Garante per la protezione dei dati personali impuso a OpenAI en diciembre de 2024 una sanción de 15 millones de euros por el tratamiento de datos en ChatGPT (Garante, 2024). El Tribunale di Roma anuló esa sanción mediante sentencia n.º 4785, de 18 de marzo de 2026, al entender que el Garante había perdido la competencia tras el reconocimiento de OpenAI Ireland como establecimiento principal en la Unión el 15 de febrero de 2024 (Diritto.it, 2026). La resolución confirma que, en aplicación del mecanismo de ventanilla única, las reclamaciones sobre ChatGPT presentadas en España se tramitan en cooperación con la autoridad irlandesa como autoridad principal.

El Comité Europeo de Protección de Datos (CEPD) publicó en mayo de 2024 el informe de su grupo de trabajo sobre ChatGPT. El informe afirma que la responsabilidad de cumplir el RGPD no debe trasladarse a los interesados mediante cláusulas de los términos y condiciones, y que OpenAI no puede alegar que la introducción de determinados datos personales estaba prohibida (CEPD, 2024, apdos. 24-25). Este criterio es relevante para valorar el papel del proveedor ante el mercado de reventa (sección 5.7).

### 2.5. Laguna que aborda este trabajo

Ninguna de estas líneas aborda la situación en la que un tercero comercializa el acceso a una cuenta de IA y, con ello, pone el contenido almacenado de cada comprador a disposición de los siguientes. Este trabajo cubre esa laguna combinando evidencia empírica con un análisis jurídico centrado en la determinación de responsabilidades.

## 3. Metodología y modelo de amenaza

El estudio es exploratorio y descriptivo: busca establecer si el fenómeno existe y cómo opera, no medir su prevalencia. Para ello se observaron cuentas reales de ChatGPT obtenidas en las mismas condiciones que cualquier comprador.

### 3.1. Diseño y obtención de la muestra

Los investigadores adquirieron acceso a cuentas de ChatGPT en plataformas de reventa de suscripciones accesibles públicamente desde España, sin recurrir a técnicas de intrusión ni a credenciales obtenidas por otras vías. Tras la compra, cada plataforma entregó los datos de acceso y los investigadores iniciaron sesión como lo haría un comprador ordinario. El trabajo de campo se desarrolló durante la primera quincena de septiembre de 2026 sobre plataformas comerciales de intermediación representativas con oferta activa en lengua española y tarificación en euros.

En cada cuenta se revisaron las secciones accesibles a cualquier usuario: el historial de conversaciones, la biblioteca de archivos e imágenes, la configuración de almacenamiento y la relación de dispositivos o sesiones vinculadas. No se emplearon herramientas automatizadas de extracción.

### 3.2. Variables observadas

Para cada plataforma y cuenta se registraron seis variables:

1. Condiciones comerciales anunciadas: precio y número de usuarios por cuenta.
2. Mecanismo de entrega del acceso: credenciales, segundo factor de autenticación y códigos de verificación por correo.
3. Número de dispositivos o accesos verificados vinculados a la cuenta.
4. Volumen de almacenamiento ocupado por archivos e imágenes.
5. Categorías de datos personales presentes, clasificadas conforme a las categorías del RGPD (sección 4.5).
6. Antigüedad relativa de la cuenta, estimada a partir del volumen y las fechas del contenido acumulado.

### 3.3. Salvaguardas éticas y jurídicas

La observación empírica conllevó necesariamente el acceso visual a datos personales de terceros alojados en las cuentas compartidas, entre los que se identificaron categorías especiales (datos de salud, art. 9 RGPD) y datos relativos a menores. Al respecto, debe precisarse que el tratamiento material desplegado por los investigadores no puede sustentarse en la consideración del artículo 85 RGPD o de la libertad de información como si constituyeran por sí mismos una base jurídica legitimadora autónoma en el sentido del artículo 6 RGPD (precepto cuya concurrencia el artículo 85 no suple de forma directa). Desde una perspectiva jurídica rigurosa, la legitimidad de la actuación investigadora debe articularse sobre un juicio de ponderación entre el ejercicio legítimo de las libertades de información e investigación científica (artículo 20.1.a y d de la Constitución española), la exigencia de necesidad y proporcionalidad estricta para documentar un riesgo sistémico de grave interés público para la colectividad, y la efectividad de las garantías aplicadas para preservar indemnes los derechos de los interesados.

Bajo este juicio de ponderación, el tratamiento se limitó estrictamente a lo indispensable para constatar la realidad y dinámica del riesgo conforme al principio de minimización (artículo 5.1.c RGPD), rigiendo las siguientes salvaguardas materiales:

- **No identificación ni contacto:** En ningún momento se intentó identificar, individualizar, perfilar ni contactar a las personas físicas cuyos datos constaban en las cuentas analizadas.
- **Inalterabilidad del entorno:** No se modificó, alteró ni eliminó contenido alguno de las cuentas durante las sesiones de observación, manteniendo intacto el estado de los repositorios y absteniéndose de ejecutar nuevas consultas o interactuar con los asistentes.
- **Minimización documental y no conservación de originales:** Las evidencias gráficas se restringieron taxativamente a las indispensables para acreditar la presencia de cada categoría de datos. No se descargaron ni conservaron en soporte local copias de los documentos, imágenes ni archivos originales ajenos.
- **Anonimización previa y exhaustiva:** Todas las capturas conservadas como evidencia probatoria fueron sometidas a anonimización inmediata y exhaustiva antes de cualquier análisis o difusión. Se tacharon de forma irreversible nombres, rostros, domicilios, números de cuenta bancaria e IBAN, identificadores de centros educativos o administrativos, perfiles de redes sociales y referencias geográficas.
- **Divulgación responsable y comunicación institucional:** Siguiendo criterios de divulgación responsable de incidentes y riesgos de seguridad, los hallazgos y evidencias se trasladaron formalmente a la Agencia Española de Protección de Datos (AEPD) en el marco de sus competencias supervisoras y de cooperación, y se pusieron en conocimiento de los canales de seguridad y privacidad del proveedor del servicio (OpenAI) con carácter previo a la difusión pública de la investigación. Se descartó expresamente cualquier comunicación a las plataformas de reventa con el fin de evitar la alteración sobrevenida, purga precipitada o destrucción intencionada de evidencias en los repositorios.

Se reconoce, no obstante, que cualquier ampliación futura de este estudio que requiera interactuar con cuentas en explotación activa debería someterse a un protocolo formal, con evaluación de impacto relativa a la protección de datos (EIPD) y la previa aprobación de un comité de ética de la investigación (sección 7).

### 3.4. Modelo de amenaza

El modelo de amenaza identifica cinco actores. El comprador anterior es el interesado cuyos datos permanecen en la cuenta. El comprador posterior accede a esos datos. El intermediario controla las credenciales y el segundo factor de autenticación, y puede entrar en la cuenta en cualquier momento. El proveedor del servicio, OpenAI, presta el servicio y conserva los datos. Por último, un atacante con fines maliciosos puede adquirir el acceso por el mismo precio que cualquier otro comprador.

Los activos expuestos son el contenido introducido por los usuarios, el perfil que el sistema deriva de ese contenido y los metadatos de la cuenta. Sobre ellos operan cinco vectores de exposición:

1. **V1. Historial de conversaciones.** Los títulos son visibles en la barra lateral y el contenido completo es accesible con un clic.
2. **V2. Biblioteca de archivos e imágenes.** Permite localizar documentos e imágenes sin leer conversaciones, lo que reduce drásticamente el esfuerzo de búsqueda.
3. **V3. Memoria y personalización.** El sistema puede incorporar a sus respuestas información procedente de conversaciones de otros usuarios de la misma cuenta. Este vector se deduce del funcionamiento documentado del servicio y no se sometió a prueba empírica.
4. **V4. Persistencia tras la baja.** Cuando el comprador deja de pagar, pierde el acceso, pero su contenido permanece en la cuenta a disposición de los siguientes.
5. **V5. Control del intermediario.** Quien gestiona las credenciales y el generador de códigos de segundo factor tiene acceso permanente a todo el contenido, y el segundo factor deja de cumplir su función de seguridad.

Estos vectores se amplifican por la agregación. Datos aislados de una misma persona, como un documento bancario, una fotografía de su vivienda y una captura con su correo electrónico, pueden combinarse en un perfil útil para el *phishing* dirigido o la recuperación fraudulenta de otras cuentas (figura 1).

## 4. Resultados

Las cuentas analizadas contenían datos de salud, financieros, administrativos, imágenes de espacios privados, información relativa a menores y credenciales, todo ello accesible para cualquier comprador posterior. Esta sección describe primero cómo opera el mercado y después qué se encontró dentro de las cuentas.

### 4.1. La oferta comercial

En una de las plataformas analizadas, el acceso a ChatGPT se ofrecía por 4,16 € al mes, junto a suscripciones de música (4,08 €) y vídeo (3,25 €), con el reclamo de ahorrar "hasta un 85 %" (figura 2). El precio oficial de ChatGPT Plus es de 20 dólares mensuales (OpenAI, s. f.-b).

Los intermediarios anunciaban habitualmente que cada suscripción se compartía entre cuatro y seis usuarios, cifra que variaba según el servicio y el plan. La oferta describía el producto como "planes oficiales de ChatGPT Plus", sin advertir de que el contenido de cada usuario quedaría accesible para los demás.

### 4.2. Un acceso automatizado que neutraliza el segundo factor

Tras la compra, la propia plataforma mostraba al cliente el correo de acceso, la contraseña y un código de verificación en dos pasos que se renovaba cada 30 segundos (figura 3). Cuando el inicio de sesión exigía un código enviado al correo de la cuenta, la plataforma también lo mostraba, con una demora de uno a dos minutos.

Este diseño tiene dos consecuencias. Primera, el intermediario conserva la semilla del generador de códigos y el acceso al buzón asociado, y puede entrar en la cuenta en cualquier momento (vector V5). Segunda, el segundo factor de autenticación, concebido para garantizar que solo el titular accede, se convierte en un mecanismo de distribución del acceso entre desconocidos.

### 4.3. Más usuarios de los anunciados

La relación de dispositivos y accesos verificados de algunas cuentas mostraba hasta 14 dispositivos vinculados a una misma cuenta, muy por encima de los cuatro a seis usuarios anunciados. Esta cifra no permite saber cuántas personas distintas habían usado la cuenta, pero indica que el número de personas con acceso al contenido podía superar ampliamente lo que el comprador esperaba.

### 4.4. Volumen de contenido almacenado

Una de las cuentas examinadas ocupaba 2,94 GB de los 20 GB de almacenamiento disponibles: 615 archivos (1,71 GB) y 1.586 imágenes (1,23 GB) (figura 4). La biblioteca de archivos e imágenes permite recorrer ese contenido directamente, sin necesidad de abrir conversaciones (vector V2).

Se observó además una diferencia clara entre cuentas recientes, con poco contenido, y cuentas de mayor antigüedad, en las que se acumulaban conversaciones, archivos e imágenes de distintos usuarios. La exposición, por tanto, crece con el tiempo de vida de la cuenta.

### 4.5. Tipología de los datos expuestos

La tabla 1 clasifica las categorías de datos observadas según su calificación en el RGPD y el riesgo principal que generan para la persona afectada.

*Tabla 1. Categorías de datos personales observadas en las cuentas compartidas.*

| Categoría | Ejemplo observado | Calificación en el RGPD | Riesgo principal |
| --- | --- | --- | --- |
| Salud | Informe de resonancia magnética craneal con hallazgos y conclusión (fig. 6) | Categoría especial (art. 9) | Discriminación, daño moral |
| Información financiera | Recibo bancario con ordenante e IBAN (fig. 7); aplicación de inversión (fig. 10) | Dato personal de riesgo elevado | Fraude, suplantación |
| Documentación administrativa | Resolución de la Seguridad Social sobre asistencia sanitaria (fig. 8) | Dato identificativo; puede revelar datos de salud | Suplantación de identidad |
| Menores | Comunicación de un centro de educación infantil; imágenes de menores | Protección específica (cdo. 38) | Localización del menor |
| Espacios privados | Interiores de viviendas y dormitorios (figs. 9 y 10) | Dato personal; vida privada | Localización, robo |
| Imagen personal | Autorretrato (fig. 10) | Dato personal | Suplantación, acoso |
| Credenciales | Capturas de formularios de alta con correo y clave (fig. 10) | Dato personal; credencial | Compromiso de otras cuentas |
| Correspondencia | Correo electrónico con un club deportivo (fig. 10) | Datos de contacto y hábitos | *Phishing* dirigido |
| Temas de conversación | Títulos que empiezan por "Pistola", "Ideolog" o "Cicatri" (fig. 5) | Pueden revelar ideología o salud (art. 9) | Perfilado |
| Documentación profesional | Presentaciones y documentos de trabajo | Datos de clientes; secretos empresariales | Daño a terceros y a la organización |

El historial de conversaciones revela por sí solo información sensible antes incluso de abrir ningún archivo (figura 5). Los títulos, generados automáticamente a partir del contenido, resumen el tema de cada consulta y son visibles en la barra lateral.

Los documentos de salud y financieros son los de mayor gravedad. El informe clínico de la figura 6 recoge una prueba de imagen craneal y sus hallazgos; el recibo bancario de la figura 7 contenía, antes de su anonimización, el nombre del ordenante, su IBAN y fragmentos de su domicilio. La figura 8 corresponde a una resolución de la Seguridad Social sobre el derecho a asistencia sanitaria.

Las imágenes de espacios privados y personales completan el perfil de los usuarios. Muestran interiores de viviendas, dormitorios, compras en curso, aplicaciones bancarias y formularios de registro con credenciales (figuras 9 y 10).

### 4.6. La exposición se intensifica tras la baja

La exposición no termina cuando el usuario deja de pagar; se intensifica. Al perder el acceso, el antiguo comprador ya no puede revisar, modificar ni eliminar lo que dejó en la cuenta, mientras sus archivos, imágenes y conversaciones siguen disponibles para quienes reciben las credenciales después (vector V4).

### 4.7. Respuesta a la PI1

Las cuentas compartidas de ChatGPT exponen a terceros desconocidos categorías especiales de datos, datos financieros e identificativos, información sobre menores y credenciales. La exposición se produce por cinco vectores, crece con la antigüedad de la cuenta y se vuelve irreversible para el usuario en el momento en que deja de tener acceso.

## 5. Análisis jurídico

El modelo de reventa genera un tratamiento de datos personales sujeto al RGPD cuyo responsable es el intermediario —específicamente respecto del tratamiento consistente en organizar y habilitar el acceso compartido al contenido almacenado en la cuenta—. Asimismo, este trabajo sostiene la tesis de que esta arquitectura técnica y comercial puede calificarse como una violación de la seguridad de los datos (en particular, de la confidencialidad en el sentido del artículo 4.12 RGPD) de carácter estructural y continuado: no un fallo técnico fortuito o accidental, sino una consecuencia intrínseca del servicio que se comercializa. La existencia de una comunicación y puesta a disposición ilícita de datos es indiscutible; la calificación complementaria como brecha de seguridad abre una discusión dogmática que esta sección fundamenta, examinando a su vez la posición de los demás actores.

### 5.1. Ámbito material: los límites de la exención doméstica

El artículo 2.2.c RGPD excluye de su ámbito el tratamiento efectuado por una persona física en el ejercicio de actividades exclusivamente personales o domésticas, que el considerando 18 vincula a la ausencia de conexión con una actividad profesional o comercial. La exención no alcanza al intermediario, cuya actividad es comercial por definición.

Más delicada es la posición del comprador que sube a la cuenta datos de terceros, como fotografías de sus hijos, informes médicos de familiares o documentos de clientes. El TJUE ha interpretado la exención de forma estricta. En *Lindqvist* declaró que no comprende la publicación en internet que hace accesibles datos a un número indeterminado de personas (STJUE de 6 de noviembre de 2003, C-101/01, apdo. 47), y en *Ryneš* subrayó que la actividad debe ser *exclusivamente* personal o doméstica (STJUE de 11 de diciembre de 2014, C-212/13).

Una cuenta en la que se observaron hasta 14 dispositivos vinculados, con compradores que rotan y no se conocen, hace accesibles los datos a un número indeterminado de personas. Por ello, la aplicación de la exención doméstica al comprador que conoce el carácter compartido de la cuenta resulta difícil de sostener. Sin embargo, la mayoría de compradores desconoce ese carácter porque la oferta lo omite (sección 4.1). Este trabajo sostiene que el peso de la responsabilidad debe recaer en quien diseña el sistema y no en quien lo padece.

### 5.2. Ámbito territorial y autoridad competente

Si el intermediario estuviera establecido en la Unión, el RGPD resultaría aplicable conforme a su artículo 3.1. En el supuesto de que opere desde fuera de la Unión (circunstancia habitual en estas plataformas de reventa, cuyo lugar de establecimiento suele permanecer opaco o radicarse en terceros países), resultará aplicable el artículo 3.2.a RGPD cuando se acredite que la oferta de servicios se dirige efectivamente a interesados que se encuentran en la Unión. A estos efectos, el considerando 23 RGPD y las directrices del CEPD identifican indicios cualificados de dicha orientación, tales como el uso de una lengua o una moneda de un Estado miembro; en la plataforma documentada, el catálogo se ofrecía en español y con precios fijados en euros (figura 2). Si bien estos elementos constituyen indicios probatorios de gran peso, su apreciación requerirá constatar en cada caso concreto la ausencia de restricciones territoriales efectivas o la existencia de pasarelas de pago orientadas a la clientela en la Unión.

Cuando resulte aplicable el artículo 3.2, el intermediario extracomunitario viene obligado a designar por escrito un representante en la Unión (artículo 27 RGPD). Las excepciones de ese precepto no resultan de aplicación, habida cuenta de que el tratamiento incluye categorías especiales de datos y no reviste carácter meramente ocasional. Al carecer de establecimiento en la Unión, el intermediario no puede beneficiarse del mecanismo de ventanilla única, por lo que la Agencia Española de Protección de Datos (AEPD) resulta plenamente competente para ejercer sus potestades respecto de los tratamientos y afectados en territorio español (artículo 55 RGPD).

La situación del proveedor es distinta. OpenAI Ireland Ltd presta el servicio a los usuarios del Espacio Económico Europeo (OpenAI, 2026), por lo que la autoridad irlandesa actúa como autoridad de control principal (artículo 56 RGPD) y la AEPD como autoridad interesada. La sentencia del Tribunale di Roma reseñada en la sección 2.4 ilustra las consecuencias de esa distribución de competencias.

### 5.3. Determinación de roles: el intermediario como responsable

Responsable del tratamiento es quien determina los fines y medios del tratamiento (artículo 4.7 RGPD). El CEPD sitúa entre los medios esenciales, cuya determinación corresponde al responsable, decidir qué datos se tratan, durante cuánto tiempo y quién tiene acceso a ellos (CEPD, 2021). El TJUE ha adoptado una concepción amplia de la noción de responsable, orientada a garantizar una protección eficaz y completa de los interesados (STJUE de 5 de junio de 2018, *Wirtschaftsakademie Schleswig-Holstein*, C-210/16; STJUE de 10 de julio de 2018, *Jehovan todistajat*, C-25/17; STJUE de 29 de julio de 2019, *Fashion ID*, C-40/17).

El intermediario decide quién accede a la cuenta, cuántas personas lo hacen y durante cuánto tiempo. También determina el medio, articulando la distribución automatizada de credenciales y códigos de verificación en dos pasos, y el fin, que es la explotación comercial de una suscripción compartida. Es, por tanto, responsable del tratamiento consistente en organizar y habilitar el acceso compartido al contenido almacenado en la cuenta, operación que el artículo 4.2 RGPD califica como comunicación "por transmisión, difusión o cualquier otra forma de habilitación de acceso". Esta delimitación es esencial: su condición de responsable se circunscribe a organizar y facilitar el acceso cruzado al repositorio acumulado, sin abarcar las operaciones de tratamiento computacional internas del asistente que ejecuta el proveedor de IA. De forma separada e independiente, el intermediario es responsable de los tratamientos asociados al registro, cobro y facturación de sus propios clientes.

OpenAI es responsable del tratamiento inherente a la prestación del servicio ChatGPT al titular formal de la cuenta. En cuanto a una eventual corresponsabilidad (artículo 26 RGPD) con el intermediario respecto del tratamiento derivado de la reventa, la existencia de una prohibición contractual de compartir cuentas en los términos de uso no determina por sí sola los roles en el RGPD. Sin embargo, a la luz de los hechos y elementos disponibles, no se aprecia una determinación conjunta o convergente de los fines y los medios del tratamiento derivado de la reventa y, por tanto, no existen elementos suficientes para apreciar corresponsabilidad entre ambos sujetos respecto de dicha actividad. Ello no exime al proveedor de sus propias obligaciones de diligencia y seguridad en el servicio que gestiona, analizadas en la sección 5.8. El origen de las cuentas revendidas y la identidad de sus titulares formales no se determinaron en este estudio.

Los compradores son, ante todo, interesados. Solo cuando suben datos de terceros podrían asumir la condición de responsables, en los términos expuestos en la sección 5.1.

### 5.4. Licitud: ausencia de base jurídica

Ninguna de las bases del artículo 6.1 RGPD ampara la comunicación del contenido de un comprador a los compradores posteriores. El consentimiento exige una manifestación de voluntad libre, específica, informada e inequívoca (artículos 4.11 y 7 RGPD), y la oferta no informa de que el contenido será visible para terceros. La ejecución del contrato tampoco sirve de base, porque el contrato tiene por objeto el acceso a un asistente de IA y la difusión del propio contenido no es necesaria para prestarlo.

El interés legítimo del artículo 6.1.f tampoco prospera. El interés comercial del intermediario no puede prevalecer sobre la confidencialidad de datos de salud o financieros, y el considerando 47 exige atender a las expectativas razonables del interesado, que no espera que desconocidos lean sus documentos.

Respecto de los datos de salud y de los que puedan revelar opiniones políticas, rige la prohibición general del artículo 9.1 RGPD y no concurre ninguna de las excepciones del artículo 9.2. Los datos de menores merecen una protección específica (considerando 38 RGPD). El artículo 84.2 LOPDGDD prevé la intervención del Ministerio Fiscal cuando la utilización o difusión de imágenes o información personal de menores en redes sociales y servicios de la sociedad de la información equivalentes pueda implicar una intromisión ilegítima en sus derechos fundamentales.

### 5.5. Transparencia

El artículo 13.1.e RGPD obliga a informar, en el momento de la recogida, de los destinatarios o categorías de destinatarios de los datos. La oferta documentada calla precisamente el dato más relevante para el comprador: que todo lo que introduzca en el servicio será visible para otros compradores, presentes y futuros. Esta omisión vulnera también el principio de transparencia del artículo 5.1.a y el deber de informar de forma concisa, transparente e inteligible del artículo 12.1.

### 5.6. Seguridad, protección por defecto y calificación como violación estructural de la confidencialidad

El artículo 25.2 RGPD exige medidas que garanticen que, por defecto, los datos personales no sean accesibles, sin la intervención de la persona, a un número indeterminado de personas físicas. El modelo de reventa opera de forma antagónica: por defecto, todo el contenido de cada usuario es accesible a un número indeterminado de compradores sucesivos. A ello se suma la infracción del principio de integridad y confidencialidad (artículo 5.1.f RGPD) y del deber de garantizar la confidencialidad permanente de los sistemas (artículo 32.1.b RGPD).

La concurrencia de una comunicación y puesta a disposición ilícita de datos personales desprovista de base legitimadora es palmaria. Adicionalmente, este trabajo sostiene la tesis de que esta arquitectura técnica puede calificarse asimismo como una violación de la seguridad de los datos —específicamente de su confidencialidad— en el sentido del artículo 4.12 RGPD. Conforme a las directrices del CEPD sobre notificación de violaciones de seguridad (CEPD, 2023), una violación de la confidencialidad concurre siempre que se produce un acceso o revelación no autorizada o ilícita a datos personales tratados. En este modelo, cada acceso de un comprador posterior al contenido acumulado de los anteriores constituye un acceso no autorizado por el interesado ni amparado por el RGPD. La singularidad jurídica radica en que dicha quiebra de la confidencialidad no dimana de un incidente técnico fortuito o externo, sino del diseño intrínseco del propio modelo comercial.

En el plano dogmático, cabe plantear que el supuesto encaja preferentemente en la infracción de los principios de licitud y transparencia de los artículos 5.1.a y 6 RGPD, debatiéndose si la figura de la brecha de seguridad exige conceptualmente un incidente sobrevenido. Este trabajo defiende que ambas calificaciones son compatibles y acumulativas. De acogerse esta calificación, su trascendencia práctica es notable al activar el régimen de los artículos 33 y 34 RGPD:

- Conforme al artículo 33 RGPD, el responsable debe evaluar la violación y proceder a su notificación a la autoridad de control competente a menos que sea improbable que entrañe un riesgo para los derechos y libertades de las personas físicas; juicio de riesgo que difícilmente resultaría inocuo ante la exposición masiva observada.
- Por su parte, el artículo 34 RGPD exige comunicar la violación a los interesados cuando sea probable que entrañe un alto riesgo para sus derechos y libertades. Dicho presupuesto de alto riesgo concurre con especial claridad ante la exposición de categorías especiales de datos (salud), datos financieros, credenciales operativas o datos de menores de edad, salvo que concurran las excepciones previstas en el artículo 34.3 RGPD.

La sentencia del TJUE de 14 de diciembre de 2023 (*Natsionalna agentsia za prihodite*, C-340/21) refuerza el análisis. El Tribunal declaró que el acceso no autorizado de terceros no basta por sí solo para considerar inapropiadas las medidas del responsable, incumbiéndole a este la carga de probar su idoneidad. No obstante, mientras en aquel litigio el acceso derivó de un ataque externo imprevisto, aquí emana del diseño organizativo habilitado por el propio intermediario, quien difícilmente podría acreditar la idoneidad de unas medidas que constituyen la causa directa de la exposición.

### 5.7. Derechos de los interesados: obstáculos arquitectónicos al ejercicio efectivo de la supresión

El comprador que abandona el servicio pierde la posibilidad de gestionar o suprimir de forma autónoma el contenido previamente volcado, y el ejercicio formal de los derechos reconocidos en el RGPD —en particular, el derecho de supresión del artículo 17 RGPD— se enfrenta a formidables obstáculos de orden práctico. Frente al intermediario, la opacidad organizativa y la frecuente ausencia de representantes identificables en la Unión privan al interesado de un interlocutor efectivo. Frente a OpenAI, la cuenta compartida consta a nombre de un titular formal distinto, lo que activa el legítimo deber del proveedor de verificar con rigor la identidad de quien pretende ejercer el derecho (artículos 11 y 12.6 RGPD); requisito que el comprador difícilmente puede satisfacer al no coincidir su identidad con los registros originarios de la cuenta.

A ello se añade que, en el funcionamiento interno del asistente, suprimir por completo una información exige eliminar de manera concurrente la memoria guardada, la conversación originaria y los archivos asociados (OpenAI, s. f.-c). En consecuencia, aunque en el plano estrictamente normativo el derecho de los interesados sigue existiendo, el modelo dificulta extraordinariamente su ejercicio efectivo y puede llegar a impedir de facto su satisfacción práctica. Esta realidad vulnera el mandato del artículo 25.1 RGPD, que exige integrar garantías eficaces para hacer efectivos los derechos de los interesados. Asimismo, la persistencia indefinida del contenido en beneficio de terceros una vez concluida la relación con el usuario vulnera el principio de limitación del plazo de conservación (artículo 5.1.e RGPD).

### 5.8. La posición del proveedor del servicio de IA

OpenAI prohíbe compartir credenciales y advierte de que hacerlo puede exponer datos personales e información de pago (OpenAI, 2026; OpenAI, s. f.-a). La cuestión es si esa prohibición basta para cumplir sus propias obligaciones como responsable del servicio. El CEPD ha señalado, a propósito de ChatGPT, que la responsabilidad de cumplir el RGPD no puede trasladarse a los interesados mediante cláusulas de los términos y condiciones (CEPD, 2024, apdos. 24-25).

Por analogía, este trabajo sostiene que la existencia de un mercado público y conocido de reventa de cuentas es un factor de riesgo que el proveedor debe ponderar al determinar las medidas apropiadas del artículo 32 y, en su caso, en la evaluación de impacto del artículo 35. El propio servicio registra los dispositivos vinculados a cada cuenta, y en las cuentas analizadas llegaron a observarse 14. Hay, por tanto, señales técnicas disponibles para detectar un uso anómalo.

No se afirma que el proveedor infrinja el RGPD; la adecuación de sus medidas debe valorarse en concreto y la carga de probarla le corresponde (C-340/21). Lo que se afirma es que la sola prohibición contractual no agota necesariamente su deber de diligencia ante un riesgo objetivamente identificable y documentado que el propio proveedor describe en su política informativa sobre cuentas compartidas (OpenAI, s. f.-a).

### 5.9. La dimensión corporativa: el uso de cuentas compartidas en el trabajo

Cuando un trabajador usa una cuenta compartida para analizar contratos, nóminas, presupuestos o correos de clientes, la organización para la que trabaja sigue siendo responsable de esos datos. No responde de forma indirecta, sino directa: el artículo 70.1 LOPDGDD sitúa a los responsables del tratamiento entre los sujetos del régimen sancionador, y el artículo 32.4 RGPD les obliga a garantizar que quienes actúan bajo su autoridad solo traten datos siguiendo sus instrucciones.

Subir esos documentos a una cuenta compartida supone ponerlos a disposición de terceros desconocidos. Para la organización, ello constituye una violación de la seguridad que le impone evaluar de inmediato el incidente y notificarlo a la autoridad de control cuando concurran los presupuestos del artículo 33 RGPD (existencia de un riesgo para los derechos y libertades de las personas físicas), dentro del plazo de 72 horas desde que tenga constancia de ella; así como comunicarlo a los afectados si la evaluación arroja un alto riesgo conforme al artículo 34 RGPD. El trabajador, por su parte, puede incurrir en un incumplimiento del deber de confidencialidad del artículo 5 LOPDGDD, extremo que dependerá de la naturaleza de la información introducida, de las instrucciones corporativas recibidas y de las circunstancias concretas del caso.

El riesgo excede la protección de datos. Una información solo constituye secreto empresarial si su titular ha adoptado medidas razonables para mantenerla en secreto (artículo 1.1 de la Ley 1/2019, de Secretos Empresariales), y tolerar el uso de herramientas no autorizadas puede debilitar esa protección. Además, desde el 2 de febrero de 2025, el artículo 4 del Reglamento (UE) 2024/1689 obliga a proveedores y responsables del despliegue de sistemas de IA a adoptar medidas para garantizar un nivel suficiente de alfabetización en IA de su personal. Una política de uso de IA que identifique herramientas autorizadas y explique los riesgos de las cuentas compartidas es el instrumento natural para cumplir ambas exigencias.

### 5.10. Otras vías de tutela

El Derecho de protección de datos no es la única vía de respuesta. Las siguientes merecen un estudio específico que excede el objeto de este trabajo:

- **Responsabilidad civil.** El artículo 82 RGPD reconoce el derecho a indemnización por daños materiales e inmateriales. Según el TJUE, el temor de un interesado a un posible uso indebido de sus datos por terceros puede constituir por sí solo un daño inmaterial (C-340/21), lo que resulta especialmente pertinente para quien sabe que sus documentos médicos siguen en una cuenta ajena. El artículo 80.1 RGPD permite a entidades sin ánimo de lucro actuar en representación de los afectados.
- **Protección de los consumidores.** Omitir que el contenido del comprador será accesible para terceros puede constituir una omisión engañosa (artículo 7 de la Ley 3/1991, de Competencia Desleal), y presentar el producto como "planes oficiales" puede inducir a error sobre su naturaleza.
- **Derecho penal.** El artículo 197.2 del Código Penal castiga a quien, sin estar autorizado, se apodere, utilice o modifique, en perjuicio de tercero, datos reservados de carácter personal registrados en soportes informáticos. El uso de la información hallada en una cuenta compartida para defraudar o suplantar a su titular podría encajar en ese tipo.
- **Relación contractual con el proveedor.** Compartir la cuenta infringe los términos de uso del proveedor, que puede suspenderla. La suspensión no resuelve la exposición y puede agravar la pérdida de control del interesado sobre su contenido.

### 5.11. Régimen sancionador aplicable

Las infracciones identificadas se distribuyen entre los dos niveles del artículo 83 RGPD. La vulneración de los principios del artículo 5, la falta de base jurídica del artículo 6, el tratamiento de categorías especiales sin excepción aplicable y la frustración de los derechos de los interesados se sitúan en el nivel superior del artículo 83.5, con multas de hasta 20 millones de euros o el 4 % del volumen de negocio anual global. Las infracciones de los artículos 25, 27, 32, 33 y 34 se sitúan en el nivel del artículo 83.4, con multas de hasta 10 millones de euros o el 2 %. La LOPDGDD califica estas conductas como muy graves o graves a efectos de prescripción (artículos 72 y 73).

### 5.12. Respuesta a la PI2 y a la PI3

El intermediario es responsable del tratamiento consistente en organizar y habilitar el acceso compartido al contenido almacenado en la cuenta, operación desprovista de base jurídica que vulnera la protección de datos por defecto y que, según se sostiene en este trabajo, puede calificarse asimismo como una violación de la confidencialidad de carácter estructural y continuado en el sentido del artículo 4.12 RGPD. De apreciarse dicha brecha, le competería evaluar el incidente y cumplir las obligaciones de notificación del artículo 33 RGPD (si existe riesgo) y de comunicación del artículo 34 RGPD (en caso de alto riesgo), así como designar un representante en la Unión cuando se acredite la aplicación extraterritorial del artículo 3.2 RGPD. El proveedor del servicio conserva sus propias obligaciones de seguridad y diligencia, que una mera prohibición contractual no agota por sí sola. Las organizaciones cuyos trabajadores usan estas cuentas responden directamente de los datos que se exponen y deben evaluar el suceso conforme al régimen de brechas de seguridad de los artículos 33 y 34 RGPD.

En cuanto a la PI3, la arquitectura del modelo dificulta extraordinariamente el ejercicio efectivo de los derechos de acceso, rectificación y supresión, pudiendo llegar a impedir de facto su satisfacción cuando el comprador ha perdido el acceso o frente al proveedor formal. Las vías más eficaces son la reclamación ante la AEPD, la acción de indemnización del artículo 82 RGPD y, de modo prioritario, la prevención.

## 6. Discusión y recomendaciones

Compartir una cuenta de IA generativa no equivale a compartir una cuenta de vídeo: lo que se comparte no es un catálogo, sino la vida documental de cada usuario. Esa diferencia explica por qué una práctica percibida como una simple infracción de condiciones de uso se convierte en un problema de protección de datos de primer orden.

### 6.1. Tres hallazgos para la discusión

**La paradoja del segundo factor.** La verificación en dos pasos se diseñó para asegurar que solo el titular accede a su cuenta. En el modelo observado, el intermediario la convierte en un mecanismo de distribución automatizada del acceso, de modo que una medida de seguridad acaba facilitando la exposición.

**La víctima también infringe.** El comprador incumple las condiciones del proveedor y, a la vez, es la principal persona perjudicada. Esta posición ambigua puede disuadirle de reclamar, y refuerza la necesidad de que la respuesta se dirija al intermediario y a la prevención, no a la sanción del usuario.

**Incompatibilidad del modelo con las exigencias del RGPD en la configuración observada.** En la configuración técnica observada, no se ha identificado una forma de operar este modelo compatible con las exigencias de licitud, confidencialidad y protección de datos por defecto del RGPD. Borrar el contenido entre compradores eliminaría también el de los usuarios simultáneos, y mantenerlo es la causa directa de la exposición. Mientras el servicio de IA almacene contenido por cuenta y no por persona, la explotación comercial del acceso compartido resulta difícilmente conciliable con los artículos 25.2 y 32 RGPD.

### 6.2. Recomendaciones por actor

La tabla 2 resume las medidas propuestas para cada actor y su fundamento.

*Tabla 2. Recomendaciones por actor.*

| Actor | Medida | Fundamento |
| --- | --- | --- |
| Usuarios | No contratar acceso compartido a asistentes de IA; usar planes oficiales con cuentas individuales | Art. 5.1.f RGPD; términos del proveedor |
| Usuarios | Si ya se usa, borrar conversaciones, archivos, imágenes y memorias antes de dejar el servicio, y no subir documentos de terceros | Control sobre los propios datos; art. 17 RGPD |
| Organizaciones | Aprobar una política de uso de IA con herramientas autorizadas e incluir el uso de cuentas no corporativas en el análisis de riesgos | Arts. 24, 32.4 RGPD; art. 1.1 Ley 1/2019 |
| Organizaciones | Formar al personal sobre los riesgos de las cuentas compartidas e integrar estos casos en el procedimiento de gestión de violaciones de seguridad para evaluar el riesgo conforme a los arts. 33 y 34 | Art. 4 Reglamento (UE) 2024/1689; arts. 33 y 34 RGPD |
| Proveedores de IA | Detectar el uso concurrente anómalo, alertar al titular de cada nuevo dispositivo y limitar las sesiones simultáneas | Arts. 25 y 32 RGPD |
| Proveedores de IA | Habilitar una vía para que quien no es titular pueda solicitar la supresión de contenido propio acreditando su autoría | Arts. 12.2 y 17 RGPD |
| Intermediarios | Cesar la actividad: en la configuración técnica observada no se ha identificado una operativa compatible con el RGPD | Arts. 6, 9, 25.2 y 32 RGPD |
| Autoridades de control | Campaña de concienciación dirigida al público y guía sobre el uso no autorizado de IA en las organizaciones | Art. 57.1.b y d RGPD |
| Autoridades de control | Actuar frente a intermediarios que se dirigen al público español y coordinarse con la autoridad principal del proveedor y con las autoridades de consumo | Arts. 3.2, 55, 56 y 61 RGPD |

### 6.3. Implicaciones para la AEPD

La AEPD tiene competencia directa sobre los intermediarios que, sin establecimiento en la Unión, se dirigen a personas en España. Una actuación de oficio sobre las plataformas que comercializan este acceso, unida a una campaña informativa, permitiría abordar el problema en su origen. Respecto del proveedor, la vía adecuada es la cooperación con la autoridad principal irlandesa para valorar si las medidas de detección de uso compartido son apropiadas al riesgo.

## 7. Limitaciones y trabajo futuro

Los resultados confirman la existencia de la práctica y documentan casos concretos de exposición, pero no permiten estimar su alcance. Las limitaciones principales son las siguientes:

- **Representatividad.** La muestra no representa necesariamente el conjunto del mercado. No se pretende establecer qué porcentaje de cuentas compartidas contiene datos sensibles.
- **Variabilidad.** Los casos observados no implican que todos los compradores introduzcan información privada ni que todas las cuentas presenten el mismo nivel de exposición. La cantidad y naturaleza de los datos dependen de la antigüedad de la cuenta, del número de usuarios, del tipo de suscripción y de los hábitos de uso.
- **Alcance de las cifras.** Los datos sobre dispositivos vinculados, volumen almacenado y antigüedad deben interpretarse exclusivamente en el contexto de la muestra examinada.
- **Un solo proveedor.** El estudio se limita a ChatGPT. Otros asistentes con almacenamiento persistente podrían presentar riesgos análogos.
- **Vector no verificado.** La exposición a través de la memoria (V3) se deduce del funcionamiento documentado del servicio, pero no se probó empíricamente.
- **Hechos no determinados.** No se estableció el origen de las cuentas revendidas ni el lugar de establecimiento de las plataformas.

El trabajo futuro debería abordar cuatro líneas. Primera, un estudio con criterios de selección definidos de antemano y una muestra suficiente para obtener conclusiones estadísticas. Segunda, la extensión a otros proveedores de IA generativa. Tercera, la verificación experimental del vector de memoria mediante cuentas controladas por los investigadores y datos sintéticos, sin acceder a datos de terceros. Cuarta, una encuesta a compradores para medir su conocimiento del riesgo. Cualquier ampliación que implique acceder a cuentas reales debería contar con evaluación de impacto y aprobación de un comité de ética.

## 8. Conclusiones

La reventa de acceso compartido a asistentes de IA generativa expone a desconocidos los datos más sensibles de sus compradores y, cuando estos se marchan, les priva de cualquier control sobre ellos. Este trabajo ha documentado el fenómeno en cuentas reales de ChatGPT, en las que se hallaron informes médicos, documentos bancarios y administrativos, imágenes de espacios privados, información sobre menores y credenciales.

Desde el punto de vista jurídico, el intermediario es responsable del tratamiento consistente en organizar y habilitar el acceso compartido al contenido almacenado en la cuenta, operación carente de base jurídica que vulnera la protección de datos por defecto del artículo 25.2 RGPD y que, según sostiene este trabajo, puede calificarse asimismo como una violación de la confidencialidad de carácter estructural y continuado en el sentido del artículo 4.12 RGPD. Si opera desde fuera de la Unión, el RGPD resultará aplicable cuando se acredite que dirige sus servicios a interesados que se encuentran en ella (artículo 3.2 RGPD), habilitando la intervención de la AEPD. El proveedor del servicio conserva sus propias obligaciones de seguridad y diligencia, que la sola prohibición contractual de compartir cuentas no agota necesariamente, y las organizaciones responden directamente de los datos que sus trabajadores exponen por esta vía, debiendo evaluar la concurrencia de los presupuestos de los artículos 33 y 34 RGPD.

En la configuración técnica observada, no se ha identificado una forma de operar este modelo compatible con las exigencias de licitud, confidencialidad y protección de datos por defecto del RGPD mientras los servicios de IA almacenen el contenido por cuenta y no por persona. La respuesta más eficaz combina la prevención, mediante la información a usuarios y organizaciones, con la actuación de las autoridades de control frente a quienes comercializan este acceso.

**Contribución de los autores.** R. V. Marcu Ungureanu: conceptualización, investigación empírica, adquisición y curación de datos, redacción del borrador original y visualización. F. Andreu Royo: conceptualización jurídica, análisis dogmático y normativo conforme al RGPD y LOPDGDD, supervisión jurídica, revisión y edición crítica del manuscrito.

**Conflicto de intereses.** Los autores declaran la inexistencia de conflictos de intereses financieros o comerciales. Se hace constar que R. V. Marcu Ungureanu es miembro de ARAINTEL Research Group, entidad editora del medio en el que se publicó un avance informativo preliminar el 22 de septiembre de 2026.

## Referencias

Fuentes en línea consultadas por última vez el 1 de octubre de 2026.

### Doctrina, informes y fuentes en línea

- Comité Europeo de Protección de Datos (CEPD). (2021). *Directrices 07/2020 sobre los conceptos de «responsable del tratamiento» y «encargado del tratamiento» en el RGPD* (versión 2.0). [Enlace](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-072020-concepts-controller-and-processor-gdpr_en)
- Comité Europeo de Protección de Datos (CEPD). (2023). *Directrices 9/2022 sobre la notificación de violaciones de la seguridad de los datos personales en virtud del RGPD* (versión 2.0). [Enlace](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-92022-personal-data-breach-notification-under_en)
- Comité Europeo de Protección de Datos (CEPD). (2024, 23 de mayo). *Report of the work undertaken by the ChatGPT Taskforce*. [Enlace](https://www.edpb.europa.eu/system/files/documents/2024-05/edpb_20240523_report_chatgpt_taskforce_en.pdf)
- Diritto.it. (2026, 3 de junio). *OpenAI, annullata la sanzione del Garante privacy*. [Enlace](https://www.diritto.it/open-ai-annullata-la-sanzione-del-garante-privacy/)
- Garante per la protezione dei dati personali. (2024, 20 de diciembre). *ChatGPT, il Garante privacy chiude l'istruttoria. OpenAI dovrà realizzare una campagna informativa di sei mesi e pagare una sanzione di 15 milioni di euro* \[Comunicado de prensa\]. [Enlace](https://www.garanteprivacy.it/home/docweb/-/docweb-display/docweb/10085432)
- Group-IB. (2023, 20 de junio). *Group-IB discovers 100K+ compromised ChatGPT accounts on dark web marketplaces* \[Comunicado de prensa\]. [Enlace](https://www.group-ib.com/media-center/press-releases/stealers-chatgpt-credentials/)
- Marcu, R. (2026, 22 de septiembre). Tu suscripción compartida de IA está filtrando tus datos. *ARAINTEL*. [Enlace](https://araintel.com/articulos/tu-suscripcion-compartida-de-ia-esta-filtrando-tus-datos/)
- Matthews, T., Liao, K., Turner, A., Berkovich, M., Reeder, R. y Consolvo, S. (2016). "She'll just grab any device that's closer": A study of everyday device & account sharing in households. En *Proceedings of the 2016 CHI Conference on Human Factors in Computing Systems*. ACM. <https://doi.org/10.1145/2858036.2858051>
- Obada-Obieh, B., Huang, Y. y Beznosov, K. (2020). The burden of ending online account sharing. En *Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems*. ACM. <https://doi.org/10.1145/3313831.3376632>
- OpenAI. (2023, 24 de marzo). *March 20 ChatGPT outage: Here's what happened*. [Enlace](https://openai.com/index/march-20-chatgpt-outage/)
- OpenAI. (2026). *Terms of Use (EU)*. Actualizados el 16 de enero de 2026. [Enlace](https://openai.com/policies/eu-terms-of-use/)
- OpenAI. (s. f.-a). *Política de uso compartido de cuentas de OpenAI*. Centro de ayuda. [Enlace](https://help.openai.com/es-es/articles/10471989-openai-account-sharing-policy)
- OpenAI. (s. f.-b). *¿Qué es ChatGPT Plus?* Centro de ayuda. [Enlace](https://help.openai.com/es-es/articles/6950777)
- OpenAI. (s. f.-c). *Memory FAQ*. Centro de ayuda. [Enlace](https://help.openai.com/en/articles/8590148-memory-faq)
- OpenAI Community. (2025, 10 de abril). *ChatGPT can now reference all past conversations*. [Enlace](https://community.openai.com/t/chatgpt-can-now-reference-all-past-conversations-april-10-2025/1229453)

### Legislación

- Reglamento (UE) 2016/679 del Parlamento Europeo y del Consejo, de 27 de abril de 2016, relativo a la protección de las personas físicas en lo que respecta al tratamiento de datos personales y a la libre circulación de estos datos (Reglamento General de Protección de Datos). [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:32016R0679)
- Reglamento (UE) 2024/1689 del Parlamento Europeo y del Consejo, de 13 de junio de 2024, por el que se establecen normas armonizadas en materia de inteligencia artificial (Reglamento de Inteligencia Artificial). [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:32024R1689)
- Ley Orgánica 3/2018, de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales. [Enlace](https://www.boe.es/buscar/act.php?id=BOE-A-2018-16673)
- Ley Orgánica 10/1995, de 23 de noviembre, del Código Penal. [Enlace](https://www.boe.es/buscar/act.php?id=BOE-A-1995-25444)
- Ley 1/2019, de 20 de febrero, de Secretos Empresariales. [Enlace](https://www.boe.es/buscar/act.php?id=BOE-A-2019-2364)
- Ley 3/1991, de 10 de enero, de Competencia Desleal. [Enlace](https://www.boe.es/buscar/act.php?id=BOE-A-1991-628)

### Jurisprudencia

- STJUE de 6 de noviembre de 2003, *Lindqvist*, C-101/01, ECLI:EU:C:2003:596. [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:62001CJ0101)
- STJUE de 11 de diciembre de 2014, *Ryneš*, C-212/13, ECLI:EU:C:2014:2428. [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:62013CJ0212)
- STJUE de 5 de junio de 2018, *Wirtschaftsakademie Schleswig-Holstein*, C-210/16, ECLI:EU:C:2018:388. [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:62016CJ0210)
- STJUE de 10 de julio de 2018, *Jehovan todistajat*, C-25/17, ECLI:EU:C:2018:551. [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:62017CJ0025)
- STJUE de 29 de julio de 2019, *Fashion ID*, C-40/17, ECLI:EU:C:2019:629. [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:62017CJ0040)
- STJUE de 14 de diciembre de 2023, *Natsionalna agentsia za prihodite*, C-340/21, ECLI:EU:C:2023:986. [Enlace](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:62021CJ0340)
- Tribunale di Roma, sentencia n.º 4785, de 18 de marzo de 2026 (citada a través de Diritto.it, 2026).

## Apéndice: Figuras

### Figura 1. Ciclo de vida de una cuenta revendida

![Figura 1. Ciclo de vida de una cuenta revendida](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-1.png)

*Figura 1. Ciclo de vida de una cuenta revendida. El intermediario conserva el acceso en todo momento y cada nuevo comprador hereda el contenido de los anteriores. Elaboración propia.*

---

### Figura 2. Catálogo de una plataforma de reventa de suscripciones

![Figura 2. Catálogo de una plataforma de reventa de suscripciones](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-2.jpeg)

*Figura 2. Catálogo de una plataforma de reventa de suscripciones. El nombre de la plataforma se ha tachado.*

---

### Figura 3. Entrega automatizada de credenciales y código de verificación

![Figura 3. Entrega automatizada de credenciales y código de verificación](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-3.jpeg)

*Figura 3. Entrega automatizada de credenciales, código de segundo factor y código de verificación por correo. Los valores se han tachado.*

---

### Figura 4. Panel de almacenamiento

![Figura 4. Panel de almacenamiento](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-4.jpeg)

*Figura 4. Panel de almacenamiento de una de las cuentas compartidas analizadas.*

---

### Figura 5. Títulos de conversaciones recientes

![Figura 5. Barra lateral con títulos de conversaciones recientes](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-5.jpeg)

*Figura 5. Títulos de conversaciones recientes de una cuenta compartida, truncados por los autores.*

---

### Figura 6. Informe clínico localizado en la biblioteca de archivos

![Figura 6. Informe clínico localizado en la biblioteca de archivos](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-6.jpeg)

*Figura 6. Informe clínico localizado en la biblioteca de archivos de una cuenta compartida.*

---

### Figura 7. Documento bancario

![Figura 7. Documento bancario anonimizado](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-7.jpeg)

*Figura 7. Documento bancario. Se han tachado ordenante, emisor, identificadores, IBAN y domicilio.*

---

### Figura 8. Resolución administrativa sobre asistencia sanitaria

![Figura 8. Resolución administrativa sobre asistencia sanitaria](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-8.jpeg)

*Figura 8. Resolución administrativa sobre asistencia sanitaria. Se han tachado los datos personales, la dirección provincial y la fecha.*

---

### Figura 9. Fotografía del interior de una vivienda

![Figura 9. Fotografía del interior de una vivienda](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-9.jpeg)

*Figura 9. Fotografía del interior de una vivienda almacenada en una cuenta compartida.*

---

### Figura 10. Mosaico de imágenes de la biblioteca de una cuenta compartida

![Figura 10. Mosaico de imágenes de la biblioteca de una cuenta compartida](images/Suscripciones%20compartidas%20de%20IA%20generativa%20como%20vector%20de%20exposici%C3%B3n%20de%20datos%20personales/figura-10.jpeg)

*Figura 10. Mosaico de imágenes de la biblioteca de una cuenta compartida: compras, formularios de registro, comunicaciones escolares, aplicaciones bancarias, correo electrónico, espacios privados e imágenes generadas. Se han tachado rostros, nombres, perfiles, dominios y datos de contacto.*
