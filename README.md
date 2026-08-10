# Monitor de uptime — cocarsagrado.com.br

Robozinho caseiro no lugar do UptimeRobot: a cada 5 minutos o GitHub Actions
dá um ping no site e avisa num Telegram privado quando o status **muda**
(caiu ou voltou).

Mora num repo público de propósito: Actions em repo público não consome a
cota mensal de minutos da conta (em repo privado, um cron de 5 min sozinho
estoura a cota e derrubaria os outros workflows junto). Aqui não vive nenhum
segredo — o token do bot fica em Actions Secrets.

- `.uptime-status` — último estado visto (`up`/`down`); só muda quando o site
  cai ou volta.
- `.heartbeat` — commit diário que impede o GitHub de desligar o cron por
  inatividade (60 dias sem commit desativa workflows agendados).
