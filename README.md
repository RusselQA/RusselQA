- 👋 Hi, I’m @RusselQA

import { Module } from '@nestjs-common';
import { SendGridModule } from '@ntegral/nestjs-sendgrid';

@Module({
  imports: [
    SendGridModule.forRoot({
      apiKey: 'my_secret_key',
    }),
  ],
})
export class AppModule {}
