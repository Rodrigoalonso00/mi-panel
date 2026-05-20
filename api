export default async function handler(req, res) {
  const url = process.env.CALENDAR_URL;
  if (!url) return res.status(500).json({ error: 'CALENDAR_URL no configurada' });

  try {
    const response = await fetch(url);
    const text = await response.text();
    res.setHeader('Access-Control-Allow-Origin', '*');
    res.setHeader('Content-Type', 'text/calendar');
    res.status(200).send(text);
  } catch (e) {
    res.status(500).json({ error: 'Error al obtener el calendario' });
  }
}
