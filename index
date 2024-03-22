const { Client } = require('whatsapp-web.js');
const qrcode = require('qrcode-terminal');

// Inicialize um cliente WhatsApp
const client = new Client();

// Evento para gerar e exibir o QR Code para fazer login
client.on('qr', qr => {
    console.log('QR Code gerado!');
    qrcode.generate(qr, { small: true });
});

// Evento de conexão bem-sucedida
client.on('ready', () => {
    console.log('O robô está operando!');
});

// Evento para receber mensagens
client.on('message', async message => {
    console.log(`Mensagem recebida de ${message.from}: ${message.body}`);

    // Responder apenas a mensagens de texto
    if (message.body.toLowerCase() === 'sim') {
        await message.reply('Obrigado pela sua confirmação.');
    } else {
        await message.reply('Obrigado por sua mensagem.');
    }
});

// Iniciar a sessão do cliente WhatsApp
client.initialize();
