# Discord-Matter — conector Rust de Matter-Rust

**Estado:** contrato definido; no hay Gateway Discord activo ni token configurado.

- Motor compartido: `Matterssmith/Base-Matter`, rama `feat/matter-rust-multiplatform`, crate `crates/matter-rust`.
- Transporte Discord: implementar con **serenity 0.12.5** (Rust) y Gateway/HTTP; token bot desde gestor de secretos, nunca en GitHub.
- Eventos: normalizar guild/channel/author/message IDs (Snowflakes), ediciones, mensajes, interacciones, slash commands, hilos y media. No mezclar con JIDs, aliases PN/LID o Telegram IDs.
- Interactividad: botones, select menus, modals y responses Discord difieren de WhatsApp NativeFlow; mapear a contrato de capacidades, con permisos de app y scopes por guild.
- Seguridad: intents mínimos, validación del autor y de eventos de Gateway, validación de firmas si hay Interactions HTTP, anti replay, rate limits, revisión de privilegios por guild. Un rol Discord no equivale a un rol global Vault.
- No ejecutar comandos de control por texto sin autorización Base+Vault. Los `@usernames` cambian; no sirven para reclamar owner global.
- Actualizaciones: monitorizar cambios oficiales Discord API/serenity, dependencias y scopes. Probar CI y E2E antes de habilitar en producción.

Pendiente: bot autenticado, gateway real, manejo de secretos y despliegue aislado; el núcleo Matter-Rust actualmente solo existe en fase offline.

Créditos:
Hecho por Lournyx Matterssmith [Lou-Nyx].
