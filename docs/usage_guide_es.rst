Guía de uso de rotki
#####################
.. toctree::
  :maxdepth: 2


Introduccion
*************

En esta sección vamos a ver cómo utilizar varias partes de la aplicación rotki.

 Primer registro
====================

Cuando inicias rotki te encuentras con un aviso de inicio de sesión/registro.

.. image:: images/rotki_login_screen.png
   :alt: Creating a new account
   :align: center

.. role:: red

Para crear una cuenta, pulse "Crear nueva cuenta" y proporcione un nombre de usuario y una contraseña:

  - **Nombre de Usuario**: es sólo un identificador para su base de datos; un usuario local.
  - **Contraseña**: :red:`No olvide esta contraseña`. Se utiliza para encriptar todos sus archivos locales.

 Si ha adquirido una suscripción premium, también puede añadir la clave de la API y el secreto aquí. Consulta la sección  :ref:`sync-data-with-rotki-server` para saber cómo sincronizar tus datos con el servidor Roki (esta opción está desactivada por     defecto).

.. image:: images/rotki_create_account.png
   :alt: Creating a new account with a premium rotki API key/secret pair
   :align: center

Todas las cuentas se crean en el directorio rotki, consulta la sección :ref:`rotki_data_directory` para saber dónde se encuentra.


Crear una nueva cuenta que restaure una base de datos respaldada (sólo para usuarios premium)
=============================================================================

Si tienes una suscripción premium y quieres crear una nueva cuenta local que restaure la base de datos respaldada, por ejemplo en un dispositivo diferente, debes añadir la clave/secreto de la API y utilizar la misma contraseña. Si la contraseña no es la misma, la apertura de la base de datos fallará.

.. image:: images/rotki_premium_signup_failed.png
   :alt: Sign-up with existing premium subscription using a wrong password
   :align: center

Consulta la sección  :ref:`sync-data-with-rotki-server`para saber más sobre cómo se comportará la suscripción premium con múltiples cuentas/dispositivos y cómo sincronizar tus datos con el servidor Roki (esta opción está desactivada por defecto).

Entrar en
=========

Si ya tienes una cuenta, sólo tienes que escribir el nombre y la contraseña en el indicador de inicio de sesión.

Configurar rotki Premium
======================

Si decides comprar rotki Premium más adelante, puedes configurarlo a través de API Keys -> rotki Premium.

.. image:: images/rotki_premium_set.png
   :alt: Set up rotki premium API key/secret pair in an existing account
   :align: center

Si después de haber configurado la prima desea reemplazar o desasociar las claves con la cuenta actualmente conectada, puede hacerlo a través de la misma página.

.. image:: images/rotki_premium_del.png
   :alt: Delete up rotki premium API key/secret pair in a premium account
   :align: center

.. _sync-data-with-rotki-server:

Sincronizar datos con rotki Server
-----------------------------

Para hacer una copia de seguridad de tus datos en el Servidor rotki activa "Permitir la sincronización de datos con el Servidor rotki". Esto te permite restaurarlos más tarde en cualquier cuenta/dispositivo siempre que se utilice :red:`la misma clave/secreto de la API y la contraseña de la cuenta`.

.. image:: images/rotki_premium_set_sync_data.png
   :alt: Sync data with rotki Server
   :align: center

Ten en cuenta que en caso de utilizar varias cuentas/dispositivos con la sincronización de datos activada, la que tenga el inicio de sesión más reciente cargará los datos más actualizados en rotki Server. Después de eso, al usar la misma cuenta desde otro dispositivo puede preguntarte si quieres reemplazar tu base de datos local por la remota.

.. image:: images/rotki_premium_replace_local_db_with_remote.png
   :alt: Replace local database with remote backup
   :align: center

También puedes mover manualmente la BD global que contiene los activos de un sistema a otro. Encuentra el :ref:`rotki_data_directory` en el sistema de origen. Asumiendo que es linux será ~/.local/share/rotki/data. La base de datos global es entonces ~/.local/share/rotki/data/global_data/global.db. Muévelo manualmente a la ubicación equivalente en el nuevo sistema.

Personalización 
**************

Esta sección contiene información sobre cómo personalizar la aplicación a través de los ajustes. Haciendo clic en el icono de usuario en la parte superior derecha y eligiendo la configuración, puede personalizar algunas opciones básicas de la aplicación.

.. _change_profit_currency:

Cambiar la moneda de las ganancias
=============================

rotki calcula todo, incluyendo su beneficio/pérdida total durante el informe PnL en una moneda fiduciaria determinada. Esto es lo que llamamos moneda_de_ganancias. Por defecto es USD. Puedes cambiar fácilmente esta configuración haciendo clic en el icono de la moneda en el menú superior derecho y cambiándola a la moneda que estés utilizando.

.. image:: images/sc_profit_currency.png
   :alt: Changing the profit currency
   :align: center

Personalizar la configuración de la aplicación
====================================

Seleccionando el botón de configuración "General" puede personalizar algunas opciones generales de la aplicación

.. image:: images/sc_general_settings.png
   :alt: Customizing the general app settings
   :align: center

Configuración general
----------------------

Análisis de uso anónimo
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Especifica si la aplicación puede enviar análisis de uso anónimos. Como aplicación local, rotki no tiene otra forma de medir cuántos usuarios activos tiene que no sea enviando alguna forma de análisis. Los datos que se envían son completamente anónimos y no contienen información sensible.

Balancear la frecuencia de guardado de datos
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Establece la frecuencia (en horas) con la que se guardarán los datos de todos los saldos. Estos datos se utilizan para calcular estadísticas y otros datos históricos para mostrar al usuario.


Formato de visualización de la fecha
^^^^^^^^^^^^^^^^^^^^

Establece el formato de visualización de las fechas en la interfaz de usuario de rotki. Uno de estos formatos es  ``%m/%d/%Y %H:%M:%S``. Esto significa mes/día/año  hora: minutos: segundos. Para ver los posibles formatos válidos compruebe aquí <https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes/>`__.

Mostrar en hora local
^^^^^^^^^^^^^^^^^^^^^^^

Elija si la hora local o UTC debe mostrarse en las exportaciones CSV, los registros de usuario en el backend y otras ubicaciones.

Límite de brecha de derivación BTC
^^^^^^^^^^^^^^^^^^^^^^^^^^

Este es el límite de la brecha de derivación que se utilizará cuando se trate de derivar direcciones de un xpub de bitcoin. Para más información consulte aquí. `here <https://blog.blockonomics.co/bitcoin-what-is-this-gap-limit-4f098e52d7e1>`__.


Configuración de la cantidad
-----------------

.. image:: images/sc_amount_settings.png
   :alt: Customizing the app's amount settings
   :align: center

Precisión flotante
^^^^^^^^^^^^^^^^^^^^

Establezca cuántos puntos decimales deben mostrarse en la interfaz de usuario para los números en coma flotante.

Moneda principal
^^^^^^^^^^^^^^^^

Lo mismo que  `cambiar la moneda de las ganancias <change_profit_currency_>`_.

Separador de miles
^^^^^^^^^^^^^^^^^^^^^^

Este es el símbolo que separará los números cada 3 dígitos para los números grandes. Por ejemplo en 1,000,000, el símbolo es ``,``.

Separador decimal
^^^^^^^^^^^^^^^^^^^^^^

Es el símbolo que separará la parte flotante del número. Por ejemplo en 5.42 el símbolo es ..``.``.

Ubicación de la moneda
^^^^^^^^^^^^^^^^^^^^

Este ajuste elige si el símbolo de la moneda se mostrará antes ($1,000) o después (1,000$) del número.

Redondeo del importe
^^^^^^^^^^^^^^^^^^

Este ajuste modifica el mecanismo de redondeo eligiendo entre Redondear hacia arriba, Redondear hacia abajo y Medio par (redondea al valor más cercano). Se puede modificar individualmente cómo se redondean los importes y los valores.

Nodos locales
------------

.. image:: images/sc_localnode_settings.png
   :alt: Customizing the app's connection to local nodes
   :align: center

Conexión a un cliente de Ethereum
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Cuando rotki se inicia intenta conectarse a un nodo local de Ethereum que se ejecuta con un puerto rpc establecido en el puerto predeterminado 8545. Si no se está ejecutando ningún cliente, todas las consultas del blockchain utilizarán un servicio externo como etherscan y esto será bastante más lento.

Si quieres conectarte a otro cliente de ethereum puedes establecer la URL y el puerto a través de la configuración. Haz clic en el icono de la persona en el menú superior derecho y selecciona "Configuración" en el menú desplegable. Esto te llevará a la página de configuración. Escriba la url/puerto deseado en el cuadro de texto ETH RPC endpoing.


Conectarse a un cliente Kusama
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Al igual que con Ethereum, aquí puedes establecer el punto final rpc de un nodo Kusama al que quieras conectarte.

Configuración de Price Oracle
---------------------

.. image:: images/sc_priceoracle_settings.png
   :alt: Customizing the app's price oracle settings
   :align: center

Aquí puede personalizar la precedencia de consulta que tendrán los oráculos de precios. Es decir, qué fuente de precios se comprobará primero, cuál en segundo lugar y así sucesivamente, tanto para los precios actuales como para los históricos.

Ajustes sólo para el frontend
-----------------------

.. image:: images/sc_frontendonly_settings1.png
   :alt: Customizing the app's frontend only settings
   :align: center

Codificación de datos
^^^^^^^^^^^^^^^

Cuando está activada, esta configuración te permite aleatorizar una gran cantidad de números, fechas y otros datos en la aplicación para que puedas compartir capturas de pantalla sin filtrar datos reales. Esta configuración no persiste a través de las sesiones.

Marco de tiempo por defecto del gráfico del tablero
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Establezca el marco de tiempo por defecto para el gráfico del tablero. Este marco de tiempo será preseleccionado al iniciar la sesión. Por defecto, recordará la selección de la sesión anterior.

Base del gráfico
^^^^^^^^^^^^^^^^^^^^^

Configure si el eje Y del gráfico comenzará en 0 o en el importe mínimo del periodo.

Actualización automática del saldo
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Activa/desactiva la actualización automática de los saldos. También establece la distancia en el tiempo entre cada actualización. La actualización automática de saldos está desactivada por defecto porque la consulta de saldos puede volverse muy lenta y además limitar la velocidad.

Consulta periódica de estado
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

El frontend de rotki consulta continuamente el backend para varios datos y actualizaciones. Esta es una operación económica que está configurada por defecto a 5 segundos. Puedes personalizar la frecuencia de esa consulta aquí.

.. image:: images/sc_frontendonly_settings2.png
   :alt: Customizing the app's frontend only settings
   :align: center

Personalización del explorador de Blockchain
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Puedes personalizar en qué explorador se abren los enlaces de transacciones y direcciones.

Tema [Premium]
^^^^^^^^^^^^^^^^^^^^
Los usuarios Premium pueden personalizar el color de los mismos para el modo claro u oscuro.


Personalización de la configuración de la contabilidad
====================================

Seleccionando el botón de configuración de "Contabilidad" puede personalizar algunas configuraciones de la aplicación que pertenecen a los cálculos contables.

Debe entender lo que hace cada ajuste, consultar con un contador de impuestos para su jurisdicción y luego establecerlos apropiadamente.

Los ajustes por defecto están establecidos por el momento para la jurisdicción fiscal alemana. Por ejemplo, todos los cálculos de ganancias/pérdidas se hacen para las operaciones sobre la base de "primero en entrar/primero en salir" y las ganancias de la venta de criptoactivos después de 1 año no están sujetas a impuestos. Estos ajustes pueden ser modificados.


Configuración de las operaciones
----------------

.. image:: images/sc_accounting_settings.png
   :alt: Customizing the accounting trade settings
   :align: center

Operaciones de cripto a cripto
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Especifique si las operaciones de cripto a cripto están sujetas a impuestos y deben tenerse en cuenta. En caso afirmativo, cada operación de cripto a cripto también crea una operación "virtual" que vende o compra el criptoactivo por fiat y luego vende o compra el fiat por el otro criptoactivo.

Costes de gas de Ethereum
^^^^^^^^^^^^^^^^^^^^^^

Especifica si los costes de gas de las transacciones de Ethereum deben contarse como pérdidas. Si se establece esto, entonces todo el ETH gastado en gas se deducirá de sus ganancias y contará como un gasto.

Período libre de impuestos
^^^^^^^^^^^^^^^^^^^^

Especifique si hay un período de tiempo y, en caso afirmativo, cuántos días, después de los cuales la posesión de un criptoactivo se considera no imponible.

Tasas por movimientos de activos
^^^^^^^^^^^^^^^^^^^^^^^

Especifique si las comisiones de depósito/retirada deben contar como gastos durante el informe de ganancias/pérdidas.

Calcular la base del coste pasado
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Cuando creamos un informe de pérdidas y ganancias también necesitamos averiguar dónde y cuándo se adquirieron todos los activos que el usuario está utilizando. Por lo que también revisamos todos los eventos pasados, incluso antes del inicio del periodo.

Este comportamiento se puede desactivar apagando este ajuste.

Configuración de los activos
--------------

.. image:: images/sc_accountingasset_settings.png
   :alt: Customizing the accounting asset settings
   :align: center


Activos ignorados
^^^^^^^^^^^^^^^

Especifique qué activos posee y desea ignorar completamente de todos los cálculos y consultas de saldo. Cualquier acción que involucre estos activos será ignorada.

.. _ledger_action_settings:

Configuración de las acciones del libro mayor
-----------------------

.. image:: images/sc_accountingledgeraction_settings.png
   :alt: Customizing the accounting ledger action settings
   :align: center

Aquí puede elegir qué tipos de acciones históricas deben considerarse imponibles y cuáles no. Por ejemplo, en Alemania los lanzamientos aéreos se consideran beneficios inesperados y no se gravan, por lo que puede especificarlo aquí.

Personalizar los datos y la configuración de seguridad
====================================


Cambiar la contraseña
---------------------

Al elegir la sección "usuario y seguridad" de los ajustes, puede cambiar la contraseña del usuario.

.. image:: images/sc_user_password_change.png
   :alt: Changing the user's password
   :align: center

Purga de datos
-----------------

rotki mantiene muchos datos en caché localmente en la base de datos del usuario. Puede ser necesario limpiar algunos de estos datos de vez en cuando. Puedes hacerlo desde la sección "Gestionar datos" de la configuración, haciendo clic en la lista desplegable, seleccionando el tipo de datos que quieres eliminar y pulsando el botón de la papelera.

.. image:: images/sc_purge_data.png
   :alt: Purging user data
   :align: center


.. _manage-historical-price-cache:

Gestionar la caché del oráculo de precios históricos
--------------------------------------------

La consulta de precios históricos desde oráculos como cryptocompare y coingecko es lenta y puede volverse más lenta como resultado de la limitación de la tasa. Por eso rotki crea cachés de precios históricos durante el tiempo de inactividad de la aplicación.

Puedes solicitar la creación de dicha caché yendo a la sección de caché de Oracle, seleccionando el oráculo, el activo de origen del par, el activo de destino del par y pulsando el botón Cachear precios del par.


.. image:: images/sc_historical_price_cache1.png
   :alt: Creating a historical price cache
   :align: center

Los usuarios también pueden gestionar las entradas de la caché de precios históricos existentes. Pueden inspeccionar cuándo comienzan los datos de precios históricos, cuándo terminan y, si lo desean, pueden eliminar la caché pulsando el botón de la papelera.

.. image:: images/sc_historical_price_cache2.png
   :alt: Managing the historical price cache
   :align: center

Personalización de la configuración de DeFi
====================================

Al elegir la sección "Defi" de la configuración puedes personalizar la configuración DeFi de la aplicación.

La ventaja de habilitar sólo los módulos que utilizas, y especificar las direcciones, es que rotki sólo consultará las direcciones especificadas para los módulos habilitados. Esto puede mejorar considerablemente la velocidad de consulta.


.. image:: images/defi_settings.png
   :alt: Changing the user's password
   :align: center


Activar/desactivar módulos
----------------------------------

Puede activar un módulo seleccionándolo en el menú desplegable que aparece al buscar en el campo de entrada "Seleccionar módulos". Un módulo activo será visible en la entrada. En la captura de pantalla anterior, por ejemplo, los módulos Compuesto y MakerDAO DSR están activos.

Para desactivar un módulo debe pulsar el botón (x) al final de la entrada.

Después de habilitar o deshabilitar un módulo es necesario volver a iniciar sesión para que los cambios surtan efecto.


Selección de direcciones
----------------------

Para limitar la consulta sólo a las direcciones seleccionadas en lugar de a todas las elegibles, puede ir a "Seleccionar cuentas" y hacer clic en el módulo que le interesa (3). La selección de direcciones del módulo (4) debería ser visible.

Busque cada dirección que le interese y luego seleccione cada una en el menú desplegable. Las direcciones seleccionadas deberían ser visibles de la misma manera que los módulos anteriores. Para eliminar una dirección debe pulsar el botón (x) al final de la entrada.

Si no se selecciona ninguna dirección para un módulo, esto significa que rotki comprobará todas las direcciones elegibles, lo que puede aumentar la duración total de la consulta.

Cambiar la configuración del backend
====================================

Los usuarios de la aplicación de escritorio pueden cambiar el directorio de datos por defecto, y el directorio de registro. Esto se puede hacer a través de la pantalla de inicio de sesión. Puedes hacer clic en la rueda dentada en la esquina inferior derecha para ver el diálogo de configuración del backend.

.. image:: images/rotki_backend_settings.png
   :alt: Change the backend settings
   :align: center

Después de seleccionar un nuevo directorio de datos, un directorio de registro, etc., puede pulsar el botón de guardar para guardar su configuración.

Tenga en cuenta que las cuentas creadas en el directorio anterior ya no serán accesibles y tendrá que moverlas manualmente a la nueva ubicación.

En la sección avanzada de la configuración del backend también puede modificar los siguientes ajustes:

- **Registro de otros módulos**: Si se activa, el registro también incluirá las entradas de registro de otras bibliotecas dependientes y no sólo de rotki. Está desactivado por defecto.
- **Sueño del bucle principal**: Esta es la cantidad de segundos que el bucle principal de rotki duerme. Está configurado por defecto a 20 segundos.
- **Tamaño máximo del registro**: Este es el tamaño máximo en megabytes que pueden tener todos los registros de una sola ejecución
- **Número máximo de archivos de registro**: Este es el número máximo de registros de respaldo (rotados) que puede tener una sola ejecución.

Importar datos
*******************

En esta sección explicaremos cómo se pueden importar datos mediante la integración con servicios externos como las bolsas de criptomonedas

Añadir una bolsa
=====================

.. image:: images/add_exchange.gif
   :alt: Add API keys for a new exchange
   :align: center

Puedes integrar muchos intercambios diferentes con rotki. Actualmente los intercambios soportados son: Kraken, Poloniex, Bittrex, Bitmex, Bitfinex, Binance, Binance US, bitcoin.de, Coinbase, Coinbase Pro, Gemini, Iconomi, Bitstamp, KuCoin, FTX.

Para ello tienes que ir a tu exchange y crear una clave API (ver la sección :ref:`api-key-permissions`).

Haz clic en "Claves API" en la barra lateral izquierda. Esto le llevará al lugar donde puede añadir nuevas claves API de intercambio. Seleccione el panel de intercambios y seleccione su intercambio en el menú desplegable. A continuación, copie y pegue la Clave API y el Secreto API en los respectivos campos de texto y pulse enviar.

Si todo ha ido bien, recibirá una confirmación de que la conexión se ha realizado correctamente. Si no es así, vuelva a comprobar que la clave y el secreto son correctos.

.. _api-key-permissions:

Permisos de la clave API
--------------------

rotki sólo necesita permisos de lectura para sus cuentas. Como regla general, los intercambios (por ejemplo, Binance, Coinbase Pro) agrupan todos los permisos de sólo lectura como "leer" o "ver".

.. image:: images/add_exchange_api_keys_binance.png
   :alt: Simple API key permissions
   :align: center

En caso de que una bolsa proporcione un esquema de permisos más granular (por ejemplo, Coinbase, Kraken) o tenga opciones adicionales (por ejemplo, límites de consulta, frase de contraseña), consulte la documentación de la bolsa o póngase en contacto a través de su canal de atención al cliente.

.. image:: images/add_exchange_api_keys_coinbase.png
   :alt: Granular API key permissions
   :align: center

También puedes probar a crear una clave de API con los permisos mínimos de lectura, luego añadirla en rotki y finalmente comprobar que la conexión fue exitosa y los datos se cargaron como se esperaba. De lo contrario, intenta de nuevo añadir más permisos de lectura.

Añadir una clave API de un servicio externo
=====================================

rotki depende de varios servicios externos para obtener datos como los precios históricos de las criptomonedas o las transacciones de Ethereum. Para obtener esos datos algunos de estos servicios requieren claves API. Así que debes ir a su página web, crear una cuenta gratuita y generar una clave API. Una vez hecho esto, puedes introducir la clave API en la sección de la página de claves API.

.. image:: images/add_external_service.gif
   :alt: Add API keys for an external service
   :align: center

Por el momento no hay una clave API obligatoria. Pero si no usas tu propio nodo las consultas de etherscan sin una clave API son realmente lentas. Así que si aún no tienes una cuenta con ellos, por favor crea una `aquí <https://etherscan.io/register>`_ y luego generar una clave de API gratuita y establecerla en la aplicación como se ha explicado anteriormente. Es gratis.

Cointracking.info
====================

También puede importar datos de `cointracking.info <https://cointracking.info/>`_ en rotki haciendo clic en "Importar datos" en el panel lateral izquierdo y siguiendo las instrucciones.

rotki puede importar cualquier dato CSV de comercio exportado desde cointracking.info. Pero en general no se recomienda utilizar cointracking ya que sus datos exportados carecen de mucha información.

.. image:: images/sc_data_import.png
   :alt: Importing data from cointracking.info
   :align: center

Saldos de Loopring
===================

Para que sus saldos de loopring sean detectados necesitará una clave API de loopring. Para obtenerla, visite `https://exchange.loopring.io/ <https://exchange.loopring.io/>`_ y desbloquear su cuenta. En el panel de la derecha tienes que hacer clic en **Exportar cuenta**.

.. image:: images/get_loopring_keys.png
   :alt: Get loopring keys
   :align: center

A continuación, en rotki tienes que añadir la clave de la API. Ve a API Keys > External Services > Loopring y pega la clave que has obtenido en la web de loopring.

.. image:: images/loopring_add_key.png
   :alt: Add loopring key
   :align: center

Después de seguir estos pasos, sus saldos en el tablero de mandos se actualizarán incluyendo la información de loopring

.. image:: images/loopring_balances.png
   :alt: Loopring balances in the UI
   :align: center


Los saldos de las cuentas de loopring también son visibles en la vista de cuentas de blockchain.

.. image:: images/loopring_balances_account.gif
   :alt: Loopring balances for an account
   :align: center

.. _track_balances: 

Seguimiento de cuentas y saldos
**********************************

Para gestionar las cuentas y los saldos (saldos de la cadena de bloques, saldos de las bolsas y saldos manuales, incluido el dinero fiduciario), debe visitar la sección "Cuentas y saldos" de la barra lateral izquierda.

.. image:: images/sc_accounts_balances.png
   :alt: Accounts & Balances page
   :align: center


Añadir saldos manuales
==================================

Con rotki también puedes añadir saldos/cuentas para cualquier tipo de activo y lugar que no esté soportado por el momento. Por ejemplo, bienes inmuebles, participaciones en acciones o participaciones en una cadena de bloques o bolsa que aún no está soportada.

Para añadir o modificar un saldo de seguimiento manual, vaya a la subpágina "Saldos manuales" y haga clic en el icono grande "+". Allí elija el activo en el menú desplegable, introduzca una etiqueta única para la cuenta, decórela con cualquier número de etiquetas y elija un importe y una ubicación.


.. image:: images/sc_manually_tracked_balances.png
   :alt: The manually tracked balances
   :align: center


Añadir y eliminar cuentas de blockchain
============================================

rotki permite hacer un seguimiento de los saldos de las cuentas de blockchain.

Para añadir o modificar una cuenta navega a la subpágina "Saldos de Blockchain" y haz clic en el icono grande "+". Ahora elige el blockchain en el que quieres añadir una cuenta (por ahora sólo son compatibles las cadenas Bitcoin, Ethereum y Kusama). A continuación, escriba o pegue la dirección en el cuadro de texto "Cuenta" y pulse el botón "Guardar".

.. image:: images/add_blockchain_balance.gif
   :alt: Add a blockchain account
   :align: center

Para dejar de rastrear una cuenta en particular, desplácese hasta las tablas de cuentas y haga clic en el icono "Eliminar" (papelera) bajo Acciones.

Si una cuenta de Ethereum también contiene tokens rastreados, puedes hacer clic en la flecha bajo "Acciones" para ampliar su vista y mostrar el desglose del saldo de la cuenta sobre todos los activos que posee.

Para Bitcoin puedes añadir direcciones manualmente o dejar que rotki las descubra usando un xpub. A partir de esta clave rotki puede generar sus direcciones y consultar la blockchain de Bitcoin para cada una de ellas hasta encontrar direcciones no utilizadas. También hay diferentes tipos de xpubs. Los xpubs P2PKH generan direcciones que tienen el "1" como prefijo, los xpubs P2SH_P2WPKH generan direcciones que comienzan con un "3" y los xpubs WPKH generan direcciones que comienzan con "bc1". Necesitarás saber qué tipo de xpub genera tu monedero bitcoin para poder elegir el tipo correcto en el menú desplegable. Si tu monedero genera un xpub prefijado con ypub o un xpub prefijado con zpub rotki puede deducir el tipo por ti automáticamente. Un xpub no permite gastar tus monedas pero proporciona información sobre tu monedero. En rotki esta información se almacena de forma segura y encriptada en su base de datos local.


.. image:: images/add_xpub_key.png
   :alt: Add a bitcoin account using XPUB
   :align: center


Checking Exchange Balances
===========================

Puede comprobar todos los saldos de activos que tiene en cada bolsa conectada en la subpágina "Saldos de bolsa". Si hace clic en el icono grande "+", accederá a la página de Claves de la API, en la que podrá gestionar sus conexiones de bolsa ( vease `Adding an exchange`_).

.. image:: images/sc_exchange_balances.png
   :alt: Exchange Balance
   :align: center


Añadir/editar etiquetas y rótulos
==============================

Puede editar cualquiera de sus cuentas de blockchain y añadir una etiqueta. La etiqueta es única para la cuenta y se mostrará en las tablas de cuentas en lugar de la dirección. La dirección se podrá seguir viendo si se pasa por encima de la etiqueta en las tablas.

.. image:: images/add_tag_label.gif
   :alt: Add a label and create a tag
   :align: center

Al pulsar el botón de edición de la cuenta también se pueden añadir etiquetas a la cuenta de blockchain. Si quieres crear una nueva etiqueta o editar una existente puedes abrir el gestor de etiquetas y elegir el nombre, la descripción y los colores de la etiqueta.


Filtrado por etiquetas
=====================

Puedes filtrar las tablas por una combinación de etiquetas.

.. image:: images/filter_by_tag.gif
   :alt: Filter the accounts by tag
   :align: center

Sólo tiene que añadir las etiquetas por las que desea filtrar en el cuadro de texto de filtro situado encima de las tablas.

Estacas ETH2
=====================

Si eres un staker de ETH2 puedes ver el valor total ganado tanto en el precio actual de ETH (2) pero también contando el precio de los pagos diarios del staking de ETH2 (3).

.. image:: images/rotki_eth2_staking.png
   :alt: See ETH2 value earned
   :align: center
   
Además puedes ver un desglose de las estadísticas diarias de validación. Cuánto ETH se ganó por día, estadísticas de atestación, estadísticas de propuesta de bloques y más.


.. image:: images/rotki_eth2_daily_stats.png
   :alt: See ETH2 value earned
   :align: center

Por último, esto también se puede tener en cuenta en el informe de pérdidas y ganancias para cualquier período de tiempo y también se puede exportar mediante CSV a una hoja de cálculo.

.. image:: images/rotki_eth2_pnl.png
   :alt: See ETH2 value earned
   :align: center

Airdrops
==========

rotki puede detectar algunos lanzamientos aéreos para usted

.. image:: images/rotki_airdrops.png
   :alt: rotki airdrops detection
   :align: center

La lista de lanzamientos aéreos admitidos actualmente es:

- Uniswap
- 1INCH
- Tornado
- Cornichon
- Grain
- Furocombo
- Lido
- Curve

Añadir eventos históricos
************************

Añadir operaciones manuales
====================

rotki sacará todo tu historial de operaciones de las bolsas cuando lo necesite. Pero la mayoría de nosotros probablemente también ha hecho algunas operaciones OTC o eventos fiscales en algún momento. Dichos eventos podrían incluso ser simplemente minar tokens, dependiendo de tu jurisdicción, participar en una ICO o recibir un pago en cripto.

En la barra lateral izquierda, haga clic en Historial y luego en el botón Operaciones del menú desplegable. Esto te llevará a la página de operaciones. Al hacer clic en el símbolo + se abrirá un menú como el siguiente.


.. image:: images/external_trade.png
   :alt: Add an external trade
   :align: center

Para añadir una nueva operación, rellene todos los campos y pulse el botón "Guardar".

En el campo de importe puede registrar el importe del activo base comprado o vendido. El campo tasa representa la tasa del activo cotizado por el activo base que se compró o vendió. Si hubo una comisión por la operación, debe introducirla en la casilla correspondiente y también introducir la moneda en la que se pagó la comisión. Este campo es opcional, por lo que si la comisión fue 0 puede dejar este campo vacío. Opcionalmente, puede proporcionar notas adicionales o incluso enlaces a exploradores de blockchain para cada operación.

En la página de operaciones puede ver una tabla de todas sus operaciones externas. Puedes editar o eliminar una operación haciendo clic en el icono correspondiente en la parte más a la derecha de cada operación bajo la columna "Acciones".

Actualmente rotki hace un seguimiento de tu saldo consultando los diferentes protocolos, bolsas y blockchains soportados. Si añades manualmente información sobre una operación, tus saldos no se actualizarán, ya que las operaciones no se consultan al actualizar los saldos de las cuentas. Si quieres actualizar manualmente tu saldo para un activo, por favor, consulta la sección :ref:`saldos manuales <track_balances>`.

Añadir acciones del libro mayor
=====================

Con las acciones del libro mayor puede añadir eventos que representen ingresos, pérdidas, gastos, etc. En la barra lateral izquierda haga clic en Historial y luego en el botón Acciones del libro mayor del menú desplegable. Puede proporcionar una ubicación, por ejemplo una bolsa, un banco, una cadena de bloques u otros. Para el tipo de acción puede seleccionar entre:

* Ingresos
* Perdida
* Donacion recibida
* Gasto
* Ingreso de dividendos
* Airdrop
* Donación
* Subvención

.. image:: images/ledger_action.png
   :alt: Add a ledger action
   :align: center

Para las acciones del libro mayor se puede especificar opcionalmente una tasa y un activo para la tasa. Esta es la tasa vinculada al activo para esta acción. Si no se indica ningún tipo, se utilizará el precio histórico en la fecha de la acción.

Al generar un informe de pérdidas y ganancias, algunas acciones del libro mayor pueden estar sujetas a impuestos en su jurisdicción y otras no. Para personalizar la lista de acciones imponibles consulte la sección :ref:`configuración de acciones del libro mayor <ledger_action_settings>`.


Personalización de la lista de activos admitidos
*********************************************

Inspección de la lista de activos
=========================

Ahora puedes gestionar la lista de activos soportados por tu instancia local de rotki. Por el momento sólo se pueden modificar los tokens de ethereum, pero a partir de las próximas versiones podrás añadir todo tipo de activos.

Puedes inspeccionar la lista de todos los activos soportados, editarlos, eliminarlos o añadir nuevos.

.. image:: images/rotki_manage_assets.png
   :alt: Manage the list of assets
   :align: center

Añadir/editar un activo
=======================

.. image:: images/rotki_add_edit_token.png
   :alt: Add or edit a custom token
   :align: center

Al pulsar el botón + en la parte superior derecha, o al editar un token existente, podrá ver el formulario de Activos.

Puede rellenar los siguientes campos:

1. La dirección del token. Es obligatorio.
2. El nombre del token. Es obligatorio.
3. El símbolo de la ficha. Es necesario.
4. Los decimales de la ficha. Es obligatorio.
5. El identificador de Coingecko. Es opcional, pero muy recomendable. Si el activo está soportado por coingecko debe obtener su identificador coingecko. Esto permitirá el uso de coingecko como un oráculo de precios y también sacará automáticamente el icono del activo de coingecko. Puede obtener el identificador coingecko de un activo buscando en esta lista: https://api.coingecko.com/api/v3/coins/list . También puede ser el mismo que la última parte de la url de coingecko. Por ejemplo desde https://www.coingecko.com/en/coins/ethereum tenemos ethereum como identificador para ETH.
6. Identificador de Cryptocompare. Esto es opcional pero se recomienda. Al menos uno de los identificadores de coingecko o cryptocompare debe ser dado para que los precios puedan ser consultados. Si no se da, se utilizará el símbolo del activo. Si no se da, no se utilizará cryptocompare. Para obtener el identificador de cryptocompare, busque la moneda en cryptocompare, visite su url y tómelo de ahí. Por ejemplo para https://www.cryptocompare.com/coins/eth/overview/USD el identificador es ETH. Siempre es lo que viene después de las monedas.
7. Puedes subir un icono para el activo. Se acepta cualquiera de las extensiones de imagen comunes (png, jpg, jpeg, webp). El icono personalizado siempre tiene preferencia sobre el autodetectado por coingecko.

Cuando introduzcas la dirección del token, rotki intentará buscar su nombre, símbolo y decimales y los utilizará si están disponibles.

También hay otros campos que son completamente opcionales y se expanden si se pulsa la sección (7) Campos opcionales.


.. image:: images/rotki_add_edit_token_optionals.png
   :alt: Optional information when adding a custom token
   :align: center

1. Puede especificar una marca de tiempo en la que el activo comenzó a existir. Esta debería ser la marca de tiempo de despliegue de los tokens.
2. Si el activo forma parte de un protocolo, especifíquelo aquí. Por ejemplo, "uniswap" para tokens de pool uniswap, "aave" para aTokens, etc.
3. Si el token se intercambia por otro token, especifíquelo aquí. Por ejemplo, LEND fue intercambiado por AAVE.
4. Un token puede tener tokens subyacentes. Como un pool, o un conjunto de tokens. Aquí se añade la dirección del token subyacente.
5. Y aquí añada el peso del token subyacente.
6. Aquí puede editar o eliminar la dirección/peso del token subyacente. Nota: El peso de los tokens subyacentes debe sumar el 100%.

Fusión de dos activos
=======================

Hay dos situaciones posibles en las que puede necesitar fusionar dos activos en uno.

1. Has añadido un activo personalizado que posteriormente ha sido soportado oficialmente en rotki. En este caso deberías fusionar tu asset personalizado con el soportado oficialmente. Si no lo haces podría dividir los saldos entre las entradas, especialmente para los intercambios soportados que utilizarán la entrada oficialmente soportada. 

2. Hubo un problema y una notificación de activo desconocido es ahora visible.

.. image:: images/rotki_merge_assets.png
   :alt: Optional information when adding a custom token
   :align: center

Para fusionar dos activos puede utilizar el diálogo de fusión pulsando el botón de fusión de activos en la pantalla de gestión de activos. En el diálogo puede poner el identificador de su activo personalizado o faltante en el campo de origen. En el caso de un activo personalizado, puede obtener el identificador utilizando el botón de copia en la tabla de activos. Si se trata de un activo ausente, puede copiarlo desde el mensaje de notificación

A continuación, puede ir al campo de destino y buscar el activo al que se fusionará el origen. Cuando el identificador de origen y el activo de destino estén seleccionados, puede pulsar el botón de fusión.

Si la fusión se realiza con éxito, se le notificará que debe volver a conectarse o actualizar los saldos manualmente para ver los cambios en el frontend.

Finanzas descentralizadas
**********************

Para seguir y analizar sus acciones DeFi utilice la pestaña de Finanzas Descentralizadas del menú de la izquierda. Puede elegir entre los diferentes tipos de acciones DeFi que se presentan en el submenú.

Préstamo
===========

En la sección de préstamos puede ver el estado de su DAI en la Tasa de Ahorro DAI (DSR). Las cuentas que utilizan el DSR se autodetectan a partir de sus cuentas de blockchain dadas. Puedes ver cuánto IAD tienes bloqueado en todas tus cuentas y cuánto IAD está bloqueado para cada cuenta en el DSR.

.. image:: images/sc_dsr_nonpremium_all.png
   :alt: DSR without premium
   :align: center

También puede filtrar por cuenta y ver cuánto IAD está bloqueado en el DSR para cada cuenta.

Si tiene una suscripción premium también puede ver cuánto IAD ha ganado en total o sobre cada cuenta, el historial de depósitos/retiradas y cuánto IAD se ganó en el momento para cada acción.

.. image:: images/sc_dsr_premium_all.png
   :alt: DSR with premium
   :align: center

Por último, es necesario tener una cuenta premium para que la cantidad total de IAD ganada en un periodo de tiempo determinado se contabilice en el informe de pérdidas y ganancias.

A continuación puede ver una pequeña demostración del uso de DSR por una cuenta premium

.. image:: images/dsr_premium_demo.gif
   :alt: DSR premium demo
   :align: center

Préstamo
=============

En la sección de préstamos puedes encontrar información sobre tus bóvedas de makerdao. Las bóvedas son autodetectadas desde tus cuentas de ethereum y se muestra información sobre cada una de ellas.

Como usuario normal no premium puedes ver todas tus bóvedas, y para cada una inspeccionar la garantía bloqueada, la colateralización, la deuda generada y el precio de liquidación.

.. image:: images/sc_vaults_nonpremium.png
   :alt: Makerdao vaults without a premium account
   :align: center


Con una suscripción premium también puede ver información adicional, como la hora de creación de la bóveda, la lista de actividades históricas, los intereses totales adeudados y los eventos de liquidación.

.. image:: images/sc_vaults_premium.png
   :alt: Makerdao vaults with a premium account
   :align: center

Los usuarios premium también pueden hacer que se tengan en cuenta los intereses de la bóveda en el informe de pérdidas y ganancias.

Por último, los usuarios premium pueden crear observadores para sus bóvedas.

.. image:: images/sc_vaults_premium_watchers.png
   :alt: Makerdao vaults with a premium account
   :align: center

Pueden añadir un ratio de colateralización objetivo que les gustaría que rotki vigilara en una bóveda. Si el ratio de colateralización es menor/mayor que ese ratio, se envía una alerta a tu correo electrónico. Este servicio de vigilancia se ejecuta en el servidor de rotki, por lo que no es necesario dejar la aplicación abierta.

A continuación puedes ver una pequeña demostración del uso de las bóvedas de makerdao por parte de una cuenta premium.

.. image:: images/vaults_premium_demo.gif
   :alt: Makerdao vaults premium demo
   :align: center

Creación de un informe de pérdidas y ganancias
*****************************

rotki crea un informe de ganancias/pérdidas para ti, basado en tus operaciones y otros eventos y en los ajustes contables proporcionados. Esto es esencialmente un cálculo de ganancias o pérdidas para todos sus eventos basados en las fechas dadas. Antes de entrar en los detalles de la generación de un informe, aquí hay algunos detalles importantes sobre el algoritmo de generación de informes:

•	Por defecto, rotki utiliza una estrategia contable llamada "First In - First Out" (abreviado: FIFO). Hay planes para implementar otras estrategias (por ejemplo, "Last In - First Out").
•	rotki permite a los usuarios de jurisdicciones que ofrecen un periodo de tenencia libre de impuestos (por ejemplo, Alemania con 1 año) especificar el periodo en días. Para ajustar este valor, consulte la sección de personalización de la configuración de la cuenta.
•	Cuando se genera un informe para un periodo personalizado, en el que rotki conoce las tenencias de cripto anteriores del usuario (por ejemplo, negociamos BTC entre los años 2017 - 2019 pero pedimos un informe entre 2018 - 2019), tiene en cuenta todas las tenencias de cripto anteriores para calcular un saldo inicial para el periodo dado. Por ejemplo, digamos que has negociado BTC entre 2017 - 2019 con un saldo de 0,1 BTC el 31 de diciembre de 2017. Al generar un informe pnl para 2018 - 2019, rotki tomará los 0,1 BTC del 31 de diciembre de 2017 como saldo inicial para sus cálculos en el periodo de 2018.

Para crear un informe de pérdidas y ganancias haz clic en el botón "Informe de pérdidas y ganancias" del menú de la izquierda. Elija un período para el informe (o haga clic en Personalizado para establecer un rango de tiempo personalizado) y pulse en "Generar" para iniciar el informe.

.. image:: images/sc_pnl_report1.png
   :alt: Overview of the profit/loss report
   :align: center

El cálculo puede llevar algún tiempo. También puede ver un resumen de la configuración contable con la que se ejecuta el informe en la sección "Configuración contable".

Si encuentra algún problema durante el informe de pérdidas y ganancias, consulte la sección :ref:`solución de problemas del informe-pnl`.

Una vez hecho esto, tiene una visión general de los beneficios/pérdidas para el período dado, cuánto de eso es imponible, y cuánto contribuye cada categoría de evento imponible al total.

Además, debajo de la visión general, se obtiene una tabla que contiene todos los eventos que se tuvieron en cuenta en el cálculo, junto con la cantidad de profit_currency que se perdió o ganó a través de ese evento.


.. image:: images/sc_pnl_report2.png
   :alt: Event list of the profit/loss report
   :align: center


Por último, puede obtener una exportación CSV pulsando el botón "Exportar CSV". Esta exportación está pensada para ser importada a Google Sheets. Pulsa el botón y luego elige un directorio en el que escribir los archivos CSV. Una vez hecho esto, puedes importar los archivos CSV a Google Sheets a través de su menú de importación. Las siguientes son las definiciones de las columnas del documento all_event
•	type es una cadena que describe el tipo de evento en el que participó el usuario, por ejemplo, en "I buy ETH for EUR", buy es el tipo.
•	location es una cadena que describe el lugar en el que se produjo el evento. Por ejemplo, "kraken" para las operaciones en kraken.
•	paid_asset es una cadena que identifica el activo en el que se pagó un evento, por ejemplo, en "compré 1 ETH por 100 EUR", EUR es el activo pagado.
•	paid_in_asset es un número que especifica la cantidad de paid_asset involucrada en un evento, por ejemplo, en "Compré 1 ETH por 100 EUR", 100 es el paid_in_asset.
•	taxable_amount: es un número que especifica la cantidad de paid_asset que debe tenerse en cuenta a efectos fiscales según la configuración de la contabilidad, por ejemplo, "Vendí 1 ETH por 120 EUR", 1 ETH es el taxable_amount.
•	received_asset es una cadena que identifica el activo del rendimiento de un evento, por ejemplo, en "Compré 1 ETH por 100 EUR", ETH es el received_asset.
•	received_in_asset es un número que especifica la cantidad de received_asset involucrada en un evento, por ejemplo, en "Compré 1 ETH por 100 EUR", 1 es el received_in_asset.
•	Beneficio_o_pérdida neto es un número que especifica la cantidad de beneficio o pérdida que supone un evento dada la estrategia contable seleccionada. Tenga en cuenta que su valor se basa en una fórmula de hoja de cálculo.
•	time es una cadena que contiene la fecha y hora en que se ejecutó un evento.
•	is_virtual es un booleano que describe si un evento es un evento generado virtualmente. Sólo aparece si se establece el ajuste de cripto a cripto. En muchas jurisdicciones, las operaciones de cripto a cripto están sujetas a impuestos al tipo de la moneda fíat equivalente. Así que siempre se genera una compra virtual adicional para una venta de cripto a cripto y lo contrario para una compra de cripto a cripto. Así, por ejemplo, la venta de BSV por BTC también haría que el usuario comprara BTC con EUR como evento virtual, asumiendo que el EUR es la moneda de beneficio establecida.
•	paid_in_XXX, donde XXX es la moneda de beneficios personalizada del usuario es un número que describe la cantidad de paid_in_asset convertida a la moneda de beneficios del usuario.
•	taxable_received_in_XXX, donde XXX es la profit_currency personalizada del usuario, es un número que describe la cantidad de received_in_asset convertida a la profit_currency del usuario. Tenga en cuenta que rotki resta adicionalmente las comisiones de negociación de una bolsa de este número.
•	taxable_bought_cost_in_EUR donde XXX es la profit_currency personalizada del usuario es un flotador que simula la cantidad total de paid_in_asset dada la estrategia contable personalizada del usuario en la profit_currency del usuario.
•	cost_basis Si se trata de un evento de gasto, este campo contiene información sobre la procedencia del importe gastado según la configuración del usuario. Qué compras contribuyeron a este gasto. Si no se conoce suficiente información, también se indica.

.. nota::
   Para obtener más información sobre profit_currency o para ajustarla, consulte la sección :ref:`change_profit_currency`.

Análisis
**********

Si tiene una suscripción premium puede obtener análisis de todos sus activos y operaciones.

.. nota::
    El punto de partida de estas analíticas será el momento en el que comenzaste a utilizar la aplicación, ya que rotki toma instantáneas del balance diariamente. También planeamos proporcionar análisis sobre los datos antes de que en una base de mejor esfuerzo como se detalla en `este <https://github.com/rotki/rotki/issues/1379>`_ tema.

Haz clic en la página de análisis en la barra lateral izquierda para ir a tu página de análisis.

Dado que rotki hace un seguimiento de todos tus activos a lo largo del tiempo, lo primero que puedes ver es un gráfico de valor/tiempo de todo tu valor neto.

.. image:: images/sc_stats_netvalue.png
   :alt: Netvalue over time graph
   :align: center

A continuación, puede ver un gráfico de la cantidad de un activo superpuesto a su valor en dólares a lo largo del tiempo. 

.. image:: images/sc_stats_asset_amount_value.png
   :alt: Asset amount and value over time
   :align: center

Además, puedes ver un gráfico circular de la distribución de tu valor neto en diferentes lugares. De este modo, puede determinar hasta qué punto está expuesto a tener una gran parte de su valor neto en las bolsas, en los bancos, etc.

.. image:: images/sc_stats_distribution_location.png
   :alt: Distribution of networth by location
   :align: center

Por último, puede ver un gráfico circular de la distribución de su valor neto entre todos los activos que posee. Se trata de una importante herramienta de análisis, ya que puede ayudarle a determinar su exposición a cada activo y a determinar si es necesario reequilibrar su cartera.

.. image:: images/sc_stats_distribution_asset.png
   :alt: Distribution of networth by asset
   :align: center

.. _set-the-backend-s-arguments:

Establecer los argumentos del backend
*******************************

rotki ejecuta un demonio python en el backend. La mayoría de las veces no necesitarás personalizar sus argumentos, pero si necesitas hacerlo, especialmente para propósitos de depuración, esto es lo que puedes hacer.

Crea o edita si existe un archivo con el nombre rotki_config.json en el mismo directorio que el ejecutable de rotki. Añade al objeto json cualquier argumento que sea también argumento de rotki. Entonces cuando rotki se inicie estos serán pasados como argumentos al backend. Un ejemplo de rotki_config.json es el siguiente:


  {
      "loglevel": "debug",
      "logfromothermodules": false,
      "log-dir": "/path/to/dir",
      "data-dir": "/path/to/dir",
      "sleep-secs": 20,
      "max_size_in_mb_all_logs": 500,
      "max_logfiles_num": 2
  }

ThLos argumentos anteriores son

- **loglevel**: Establece el nivel de registro para la aplicación. Los valores válidos son: 'debug', 'info', 'warn', 'error', 'critical'.
- **logfromothermodules**: Si aparece este argumento, el registro también incluirá entradas de registro de otras bibliotecas dependientes y no sólo de rotki. Por defecto es falso.
- **log-dir**: El nombre para el directorio de registro.
- **data-dir**: La ruta del directorio donde se guardarán todos los datos de rotki. El valor por defecto depende del sistema operativo del usuario. Comprueba la siguiente sección
- **sleep-secs**: Esta es la cantidad de segundos que el bucle principal de rotki duerme. Por defecto es 20.
- **max_size_in_mb_all_logs**: Este es el tamaño máximo en megabytes que pueden tener todos los registros de una sola ejecución
- **max_logfiles_num**: Es el número máximo de registros de respaldo (rotados) que puede tener una sola ejecución.

.. _rotki_data_directory:

directorio de datos de rotki
***********************

rotki guarda los datos del usuario por defecto en un directorio diferente por cada sistema operativo. Para cada sistema operativo los datos se guardan en el directorio equivalente a los estándares respectivos.

- **Linux**: ``~/.local/share/rotki/data/``
- **OSX**: ``~/Library/Application Support/rotki/data``
- **Windows**: ``%LOCALAPPDATA%/rotki/data``

Antes de la v1.6.0 rotki guardaba los datos en $USER/.rotkehlchen. A partir de la v1.6.0 ese directorio se migró al directorio estándar equivalente al del sistema operativo y debería ser seguro para los usuarios borrar el antiguo directorio siempre y cuando el nuevo directorio contenga la DB migrada.

Una muy buena idea sobre el directorio de datos de rotki sería hacer copias de seguridad frecuentes de él, ya que contiene todos los datos de todas sus cuentas de rotki y los datos de caché para las consultas de precios históricos.

Solución de problemas
*****************

Error de falta de gas durante eth_call
========================================

Si ves un error como el siguiente


 [17/12/2020 18:31:29 CET] WARNING rotkehlchen.chain.ethereum.manager: Failed to query own node for <bound method EthereumManager._call_contract of <rotkehlchen.chain.ethereum.manager.EthereumManager object at 0x7f4b16b8bc90>> due to Error doing call on contract 0x06FE76B2f432fdfEcAEf1a7d4f6C3d41B5861672: {'code': -32000, 'message': 'out of gas'}
 
mientras rotki está consultando su nodo local geth para algo, entonces significa que la consulta ha alcanzado el límite de gas.
Puedes arreglar esto simplemente añadiendo el argumento --rpc.gascap 0 a tu nodo geth. Esto tendrá un gascap ilimitado. Tenga cuidado si es un nodo expuesto al público, ya que esto puede permitir que una eth_call maliciosa bloquee su nodo.

El reloj del sistema local no está sincronizado
========================================

Algunos servidores remotos (por ejemplo, las centrales) requieren que el reloj de tu sistema local esté sincronizado con el suyo. En caso de no tenerlo sincronizado la petición fallará y rotki mostrará un mensaje de error específico (es decir, un código de estado 409 y un mensaje de que el reloj del sistema local no está sincronizado) o el genérico de error 500 (por favor, :ref:`reportar a nosotros <bug_reporting>`).

Siga las directrices oficiales de su sistema operativo sobre cómo sincronizar el reloj con un servidor de tiempo de Internet y vuelva a intentarlo.


La restauración de la base de datos respaldada en la creación de una nueva cuenta falla
============================================================

Por favor, asegúrese de que está utilizando las claves/secreto de la API de su suscripción premium y la misma contraseña.

Los datos con múltiples cuentas/dispositivos no se sincronizan
===================================================

Por favor, asegúrate de que todas tus cuentas tienen activada la opción "Permitir la sincronización de datos con rotki Server", y que en cada inicio de sesión haces la elección apropiada cuando se te pide que reemplaces la base de datos local. Consulta la sección :ref:`sync-data-with-rotki-server` para más información sobre cómo sincronizar los datos con múltiples cuentas/dispositivos.

.. _troubleshooting-pnl-report:

Problemas de creación de informes de pérdidas y ganancias
===========================================

Tiempo de espera o precio no encontrado para la marca de tiempo
-------------------------------------------------

Averigüe qué activo causó el precio no encontrado. A continuación, compruebe las cachés de precios históricos y asegúrese de que tiene creada la caché de precios históricos para ese par de activos. Por ejemplo, si está creando un informe de pérdidas y ganancias en GBP y el activo es GNO, asegúrese de crear la caché de precios históricos GNO -> GBP. Ver :ref:`manage-historical-price-cache` para saber cómo hacerlo
